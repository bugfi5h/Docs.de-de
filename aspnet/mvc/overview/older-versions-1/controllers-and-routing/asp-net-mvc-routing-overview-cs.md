---
uid: mvc/overview/older-versions-1/controllers-and-routing/asp-net-mvc-routing-overview-cs
title: "ASP.NET MVC-Routing-Übersicht (c#) | Microsoft Docs"
author: StephenWalther
description: In diesem Lernprogramm wird Stephen Walther gezeigt, wie das ASP.NET MVC-Framework Browseranforderungen Controlleraktionen zugeordnet.
ms.author: aspnetcontent
manager: wpickett
ms.date: 08/19/2008
ms.topic: article
ms.assetid: 5b39d2d5-4bf9-4d04-94c7-81b84dfeeb31
ms.technology: dotnet-mvc
ms.prod: .net-framework
msc.legacyurl: /mvc/overview/older-versions-1/controllers-and-routing/asp-net-mvc-routing-overview-cs
msc.type: authoredcontent
ms.openlocfilehash: 714fd1939ffeba11b84a82e80193ecbbe4b12e09
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2017
---
<a name="aspnet-mvc-routing-overview-c"></a><span data-ttu-id="73789-103">ASP.NET MVC-Routing-Übersicht (c#)</span><span class="sxs-lookup"><span data-stu-id="73789-103">ASP.NET MVC Routing Overview (C#)</span></span>
====================
<span data-ttu-id="73789-104">durch [Stephen Walther](https://github.com/StephenWalther)</span><span class="sxs-lookup"><span data-stu-id="73789-104">by [Stephen Walther](https://github.com/StephenWalther)</span></span>

> <span data-ttu-id="73789-105">In diesem Lernprogramm wird Stephen Walther gezeigt, wie das ASP.NET MVC-Framework Browseranforderungen Controlleraktionen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="73789-105">In this tutorial, Stephen Walther shows how the ASP.NET MVC framework maps browser requests to controller actions.</span></span>


<span data-ttu-id="73789-106">In diesem Lernprogramm werden Sie eine Einführung in ein wichtiges Feature von jeder ASP.NET MVC-Anwendung namens *ASP.NET-Routing*.</span><span class="sxs-lookup"><span data-stu-id="73789-106">In this tutorial, you are introduced to an important feature of every ASP.NET MVC application called *ASP.NET Routing*.</span></span> <span data-ttu-id="73789-107">Das ASP.NET-Routing-Modul ist verantwortlich für die Zuordnung von eingehenden Browseranforderungen zu bestimmten Aktionen von MVC-Controller.</span><span class="sxs-lookup"><span data-stu-id="73789-107">The ASP.NET Routing module is responsible for mapping incoming browser requests to particular MVC controller actions.</span></span> <span data-ttu-id="73789-108">Am Ende dieses Lernprogramms können Sie verstehen, wie die standardmäßigen Routentabelle Controlleraktionen Anforderungen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="73789-108">By the end of this tutorial, you will understand how the standard route table maps requests to controller actions.</span></span>

## <a name="using-the-default-route-table"></a><span data-ttu-id="73789-109">Mithilfe der Standardroute-Tabelle</span><span class="sxs-lookup"><span data-stu-id="73789-109">Using the Default Route Table</span></span>

<span data-ttu-id="73789-110">Wenn Sie eine neue ASP.NET MVC-Anwendung erstellen, wird die Anwendung bereits ASP.NET-Routing Verwendung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="73789-110">When you create a new ASP.NET MVC application, the application is already configured to use ASP.NET Routing.</span></span> <span data-ttu-id="73789-111">ASP.NET-Routing funktioniert Setup an zwei Stellen.</span><span class="sxs-lookup"><span data-stu-id="73789-111">ASP.NET Routing is setup in two places.</span></span>

<span data-ttu-id="73789-112">ASP.NET-Routing ist zunächst in der Webkonfigurationsdatei (Datei "Web.config") für Ihre Anwendung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="73789-112">First, ASP.NET Routing is enabled in your application's Web configuration file (Web.config file).</span></span> <span data-ttu-id="73789-113">Es gibt vier Abschnitte in der Konfigurationsdatei, die für routing relevant sind: Abschnitt system.web.httpModules, Abschnitt system.web.httpHandlers Abschnitt system.webserver.modules und Abschnitt system.webserver.handlers.</span><span class="sxs-lookup"><span data-stu-id="73789-113">There are four sections in the configuration file that are relevant to routing: the system.web.httpModules section, the system.web.httpHandlers section, the system.webserver.modules section, and the system.webserver.handlers section.</span></span> <span data-ttu-id="73789-114">Achten Sie darauf, dass Sie nicht in diesen Abschnitten gelöscht werden, da ohne diese Abschnitte routing nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="73789-114">Be careful not to delete these sections because without these sections routing will no longer work.</span></span>

<span data-ttu-id="73789-115">Zweitens und wichtiger ist, wird eine Routingtabelle in die Datei "Global.asax" der Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="73789-115">Second, and more importantly, a route table is created in the application's Global.asax file.</span></span> <span data-ttu-id="73789-116">Die Datei "Global.asax" ist eine spezielle Datei, die Ereignishandler für die Lebenszyklusereignisse von ASP.NET Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="73789-116">The Global.asax file is a special file that contains event handlers for ASP.NET application lifecycle events.</span></span> <span data-ttu-id="73789-117">Die Routingtabelle wird während des Ereignisses zum Starten der Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="73789-117">The route table is created during the Application Start event.</span></span>

<span data-ttu-id="73789-118">Die Datei im Codebeispiel 1 enthält die standardmäßige Datei "Global.asax" einer ASP.NET MVC-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="73789-118">The file in Listing 1 contains the default Global.asax file for an ASP.NET MVC application.</span></span>

<span data-ttu-id="73789-119">**1 – Global.asax.cs auflisten**</span><span class="sxs-lookup"><span data-stu-id="73789-119">**Listing 1 - Global.asax.cs**</span></span>

[!code-csharp[Main](asp-net-mvc-routing-overview-cs/samples/sample1.cs)]

<span data-ttu-id="73789-120">Wenn eine MVC-Anwendung zuerst gestartet wird, die Anwendung\_Start()-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="73789-120">When an MVC application first starts, the Application\_Start() method is called.</span></span> <span data-ttu-id="73789-121">Diese Methode ruft wiederum die RegisterRoutes()-Methode.</span><span class="sxs-lookup"><span data-stu-id="73789-121">This method, in turn, calls the RegisterRoutes() method.</span></span> <span data-ttu-id="73789-122">Die RegisterRoutes()-Methode erstellt die Routentabelle.</span><span class="sxs-lookup"><span data-stu-id="73789-122">The RegisterRoutes() method creates the route table.</span></span>

<span data-ttu-id="73789-123">Die Standard-Routingtabelle enthält eine einzelne Route (mit dem Namen "Default").</span><span class="sxs-lookup"><span data-stu-id="73789-123">The default route table contains a single route (named Default).</span></span> <span data-ttu-id="73789-124">Die Standardroute ordnet das erste Segment einer URL Controllernamen, das zweite Segment der URL zu einem Controlleraktion und das dritte Segment, das einen Parameter namens **Id**.</span><span class="sxs-lookup"><span data-stu-id="73789-124">The Default route maps the first segment of a URL to a controller name, the second segment of a URL to a controller action, and the third segment to a parameter named **id**.</span></span>

<span data-ttu-id="73789-125">Stellen Sie sich vor, dass Sie die folgende URL in die Adressleiste des Webbrowsers eingeben:</span><span class="sxs-lookup"><span data-stu-id="73789-125">Imagine that you enter the following URL into your web browser's address bar:</span></span>

<span data-ttu-id="73789-126">/ Home/Index/3</span><span class="sxs-lookup"><span data-stu-id="73789-126">/Home/Index/3</span></span>

<span data-ttu-id="73789-127">Die Standardroute ordnet diese URL die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="73789-127">The Default route maps this URL to the following parameters:</span></span>

- <span data-ttu-id="73789-128">Controller = Home</span><span class="sxs-lookup"><span data-stu-id="73789-128">controller = Home</span></span>

- <span data-ttu-id="73789-129">Aktion = Index</span><span class="sxs-lookup"><span data-stu-id="73789-129">action = Index</span></span>

- <span data-ttu-id="73789-130">ID = 3</span><span class="sxs-lookup"><span data-stu-id="73789-130">id = 3</span></span>

<span data-ttu-id="73789-131">Wenn Sie die URL/Home/Index/3 anfordern, wird der folgende Code ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="73789-131">When you request the URL /Home/Index/3, the following code is executed:</span></span>

<span data-ttu-id="73789-132">HomeController.Index(3)</span><span class="sxs-lookup"><span data-stu-id="73789-132">HomeController.Index(3)</span></span>

<span data-ttu-id="73789-133">Die Standardroute enthält Standardwerte für alle drei Parameter.</span><span class="sxs-lookup"><span data-stu-id="73789-133">The Default route includes defaults for all three parameters.</span></span> <span data-ttu-id="73789-134">Wenn Sie einen Domänencontroller nicht angeben, klicken Sie dann den Controller Parameter ist standardmäßig auf den Wert **Home**.</span><span class="sxs-lookup"><span data-stu-id="73789-134">If you don't supply a controller, then the controller parameter defaults to the value **Home**.</span></span> <span data-ttu-id="73789-135">Wenn Sie eine Aktion angeben, wird standardmäßig der Action-Parameter auf den Wert **Index**.</span><span class="sxs-lookup"><span data-stu-id="73789-135">If you don't supply an action, the action parameter defaults to the value **Index**.</span></span> <span data-ttu-id="73789-136">Schließlich, wenn Sie eine Id angeben, wird standardmäßig der Id-Parameter auf eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="73789-136">Finally, if you don't supply an id, the id parameter defaults to an empty string.</span></span>

<span data-ttu-id="73789-137">Sehen wir uns einige Beispiele, wie die Standardroute URLs Controlleraktionen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="73789-137">Let's look at a few examples of how the Default route maps URLs to controller actions.</span></span> <span data-ttu-id="73789-138">Stellen Sie sich vor, dass Sie die folgende URL in der Adressleiste des Browsers eingeben:</span><span class="sxs-lookup"><span data-stu-id="73789-138">Imagine that you enter the following URL into your browser address bar:</span></span>

<span data-ttu-id="73789-139">/ Start</span><span class="sxs-lookup"><span data-stu-id="73789-139">/Home</span></span>

<span data-ttu-id="73789-140">Aufgrund der Standardeinstellung Route Parameterstandardwerte wird diese URL eingeben der Index()-Methode der HomeController-Klasse auflisten verursachen in 2 aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="73789-140">Because of the Default route parameter defaults, entering this URL will cause the Index() method of the HomeController class in Listing 2 to be called.</span></span>

<span data-ttu-id="73789-141">**Auflisten von 2 – HomeController.cs**</span><span class="sxs-lookup"><span data-stu-id="73789-141">**Listing 2 - HomeController.cs**</span></span>

[!code-csharp[Main](asp-net-mvc-routing-overview-cs/samples/sample2.cs)]

<span data-ttu-id="73789-142">Auflisten von 2 umfasst HomeController-Klasse eine Methode namens Index(), die einen einzelnen Parameter mit dem Namen ID akzeptiert Die URL/Home bewirkt, dass die Index()-Methode, die mit einer leeren Zeichenfolge als Wert des Id-Parameters aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="73789-142">In Listing 2, the HomeController class includes a method named Index() that accepts a single parameter named Id. The URL /Home causes the Index() method to be called with an empty string as the value of the Id parameter.</span></span>

<span data-ttu-id="73789-143">Aufgrund der Art und Weise, dass das MVC-Framework Controlleraktionen aufruft entspricht der URL/Home auch die Index()-Methode der HomeController-Klasse in 3 auflisten.</span><span class="sxs-lookup"><span data-stu-id="73789-143">Because of the way that the MVC framework invokes controller actions, the URL /Home also matches the Index() method of the HomeController class in Listing 3.</span></span>

<span data-ttu-id="73789-144">**Auflisten von 3 – HomeController.cs (Index-Aktion ohne Parameter)**</span><span class="sxs-lookup"><span data-stu-id="73789-144">**Listing 3 - HomeController.cs (Index action with no parameter)**</span></span>

[!code-csharp[Main](asp-net-mvc-routing-overview-cs/samples/sample3.cs)]

<span data-ttu-id="73789-145">Die Methode Index() in 3 auflisten akzeptiert keine Parameter.</span><span class="sxs-lookup"><span data-stu-id="73789-145">The Index() method in Listing 3 does not accept any parameters.</span></span> <span data-ttu-id="73789-146">Die URL/Home führt dazu, dass diese Index()-Methode aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="73789-146">The URL /Home will cause this Index() method to be called.</span></span> <span data-ttu-id="73789-147">Die URL/Home/Index/3 ruft auch diese Methode (die Id wird ignoriert).</span><span class="sxs-lookup"><span data-stu-id="73789-147">The URL /Home/Index/3 also invokes this method (the Id is ignored).</span></span>

<span data-ttu-id="73789-148">Die URL/Home entspricht auch der Index()-Methode der HomeController-Klasse in 4 auflisten.</span><span class="sxs-lookup"><span data-stu-id="73789-148">The URL /Home also matches the Index() method of the HomeController class in Listing 4.</span></span>

<span data-ttu-id="73789-149">**Auflisten von 4 – HomeController.cs (Index-Aktion mit NULL-Werte zulassen-Parameter)**</span><span class="sxs-lookup"><span data-stu-id="73789-149">**Listing 4 - HomeController.cs (Index action with nullable parameter)**</span></span>

[!code-csharp[Main](asp-net-mvc-routing-overview-cs/samples/sample4.cs)]

<span data-ttu-id="73789-150">Auflisten von 4 hat die Index()-Methode einen ganzzahligen Parameter an.</span><span class="sxs-lookup"><span data-stu-id="73789-150">In Listing 4, the Index() method has one Integer parameter.</span></span> <span data-ttu-id="73789-151">Da der Parameter ein NULL-Werte zulassen-Parameter ist (kann den Wert Null haben), kann die Index() aufgerufen werden, ohne einen Fehler auszulösen.</span><span class="sxs-lookup"><span data-stu-id="73789-151">Because the parameter is a nullable parameter (can have the value Null), the Index() can be called without raising an error.</span></span>

<span data-ttu-id="73789-152">Schließlich Aufrufen der Methode Index() 5 auflisten, mit der URL/Home führt dazu, dass eine Ausnahme seit dem Id-Parameter *nicht* Parameter NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="73789-152">Finally, invoking the Index() method in Listing 5 with the URL /Home causes an exception since the Id parameter *is not* a nullable parameter.</span></span> <span data-ttu-id="73789-153">Wenn Sie versuchen, das Aufrufen der Methode Index() erhalten Sie den Fehler, die in Abbildung 1 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="73789-153">If you attempt to invoke the Index() method then you get the error displayed in Figure 1.</span></span>

<span data-ttu-id="73789-154">**Auflisten von 5 – HomeController.cs (Index-Aktion mit der Id-Parameter)**</span><span class="sxs-lookup"><span data-stu-id="73789-154">**Listing 5 - HomeController.cs (Index action with Id parameter)**</span></span>

[!code-csharp[Main](asp-net-mvc-routing-overview-cs/samples/sample5.cs)]


<span data-ttu-id="73789-155">[![Eine Controlleraktion aufrufen, die einen Parameterwert erwartet](asp-net-mvc-routing-overview-cs/_static/image1.jpg)](asp-net-mvc-routing-overview-cs/_static/image1.png)</span><span class="sxs-lookup"><span data-stu-id="73789-155">[![Invoking a controller action that expects a parameter value](asp-net-mvc-routing-overview-cs/_static/image1.jpg)](asp-net-mvc-routing-overview-cs/_static/image1.png)</span></span>

<span data-ttu-id="73789-156">**Abbildung 01**: Aufrufen einer Controlleraktion, die einen Parameterwert erwartet ([klicken Sie hier, um das Bild in voller Größe angezeigt](asp-net-mvc-routing-overview-cs/_static/image2.png))</span><span class="sxs-lookup"><span data-stu-id="73789-156">**Figure 01**: Invoking a controller action that expects a parameter value ([Click to view full-size image](asp-net-mvc-routing-overview-cs/_static/image2.png))</span></span>


<span data-ttu-id="73789-157">URL/Home/Index/3 funktioniert andererseits, problemlos mit Index-Controlleraktion 5 auflisten.</span><span class="sxs-lookup"><span data-stu-id="73789-157">The URL /Home/Index/3, on the other hand, works just fine with the Index controller action in Listing 5.</span></span> <span data-ttu-id="73789-158">Die Anforderung /Home/Index/3 bewirkt, dass die Index()-Methode, die mit einem Id-Parameter aufgerufen werden, die den Wert 3 hat.</span><span class="sxs-lookup"><span data-stu-id="73789-158">The request /Home/Index/3 causes the Index() method to be called with an Id parameter that has the value 3.</span></span>

## <a name="summary"></a><span data-ttu-id="73789-159">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="73789-159">Summary</span></span>

<span data-ttu-id="73789-160">Das Ziel dieses Lernprogramms wurde eine kurze Einführung in ASP.NET-Routing stellen.</span><span class="sxs-lookup"><span data-stu-id="73789-160">The goal of this tutorial was to provide you with a brief introduction to ASP.NET Routing.</span></span> <span data-ttu-id="73789-161">Untersucht die Standard-Routingtabelle, die Sie durch eine neue ASP.NET MVC-Anwendung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="73789-161">We examined the default route table that you get with a new ASP.NET MVC application.</span></span> <span data-ttu-id="73789-162">Sie haben gelernt, wie die Standardroute URLs Controlleraktionen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="73789-162">You learned how the default route maps URLs to controller actions.</span></span>

>[!div class="step-by-step"]
[<span data-ttu-id="73789-163">Nächste</span><span class="sxs-lookup"><span data-stu-id="73789-163">Next</span></span>](understanding-action-filters-cs.md)