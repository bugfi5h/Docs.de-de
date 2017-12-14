---
uid: single-page-application/overview/templates/breezeknockout-template
title: Kinderspiel/Knockout Vorlage | Microsoft Docs
author: madskristensen
description: Vorlage zum Kinderspiel/Knockout einseitigen-Anwendung
ms.author: aspnetcontent
manager: wpickett
ms.date: 01/30/2013
ms.topic: article
ms.assetid: 3bd94827-3c59-448f-abc3-36e6df4858db
ms.technology: 
ms.prod: .net-framework
msc.legacyurl: /single-page-application/overview/templates/breezeknockout-template
msc.type: authoredcontent
ms.openlocfilehash: 07ec099a0381458fe42c1972a2554f76fd34638c
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2017
---
<a name="breezeknockout-template"></a><span data-ttu-id="f4e92-103">Kinderspiel/Knockout-Vorlage</span><span class="sxs-lookup"><span data-stu-id="f4e92-103">Breeze/Knockout template</span></span>
====================
<span data-ttu-id="f4e92-104">durch [Mads Kristensen](https://github.com/madskristensen)</span><span class="sxs-lookup"><span data-stu-id="f4e92-104">by [Mads Kristensen](https://github.com/madskristensen)</span></span>

> <span data-ttu-id="f4e92-105">Die Kinderspiel/Knockout MVC-Vorlage wurde vom Ward Bell geschrieben.</span><span class="sxs-lookup"><span data-stu-id="f4e92-105">The Breeze/Knockout MVC Template was written by Ward Bell</span></span>
> 
> [<span data-ttu-id="f4e92-106">Herunterladen der Kinderspiel/Knockout MVC-Vorlage</span><span class="sxs-lookup"><span data-stu-id="f4e92-106">Download the Breeze/Knockout MVC Template</span></span>](https://go.microsoft.com/fwlink/?LinkId=282649)


<span data-ttu-id="f4e92-107">Sie haben "einseitige Anwendung" gehört (SPA) und gefragt, was ist.</span><span class="sxs-lookup"><span data-stu-id="f4e92-107">You've heard of "single page application" (SPA) and wondered what it is.</span></span> <span data-ttu-id="f4e92-108">Während Sie Informationen lesen konnte, würden Sie stattdessen für sich selbst fest.</span><span class="sxs-lookup"><span data-stu-id="f4e92-108">While you could read about it, you'd rather experience it for yourself.</span></span> <span data-ttu-id="f4e92-109">Aber wer ist Zeit, um ein Beispiel herunterladen möchten?</span><span class="sxs-lookup"><span data-stu-id="f4e92-109">But who has time to download a sample?</span></span> <span data-ttu-id="f4e92-110">Wenn Sie Visual Studio haben, stehen Ihnen ein Beispiel für SPA einrichten und ausführen, in weniger als 60 Sekunden mit ASP.NET-MVC 4 "Kinderspiel/Knockout einseitigen-Anwendung" Vorlage.</span><span class="sxs-lookup"><span data-stu-id="f4e92-110">If you've got Visual Studio, you'll have an example SPA up and running in less than 60 seconds with the ASP.NET MVC 4 "Breeze/Knockout Single Page Application" template.</span></span>

![](http://www.breezejs.com/sites/all/images/spa-template/ZephyrRunning.png)

## <a name="what-is-the-breezeknockout-spa-template"></a><span data-ttu-id="f4e92-111">Was ist die Kinderspiel/Knockout SPA-Vorlage?</span><span class="sxs-lookup"><span data-stu-id="f4e92-111">What is the Breeze/Knockout SPA Template?</span></span>

<span data-ttu-id="f4e92-112">Die meisten Projektvorlagen Generieren einer Anwendung Skeleton.</span><span class="sxs-lookup"><span data-stu-id="f4e92-112">Most project templates generate an application skeleton.</span></span> <span data-ttu-id="f4e92-113">Sie Flesh auf diese Gerüst durch Hinzufügen von Code und schließlich eine funktionierende Anwendung zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="f4e92-113">You put flesh on those bones by adding your code and eventually deliver a working application.</span></span> <span data-ttu-id="f4e92-114">Die Vorlage zum Kinderspiel/Knockout SPA unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="f4e92-114">The Breeze/Knockout SPA template is different.</span></span> <span data-ttu-id="f4e92-115">Es wird eine beispielanwendung zu untersuchen, das Sie generiert.</span><span class="sxs-lookup"><span data-stu-id="f4e92-115">It generates a sample application for you to study.</span></span> <span data-ttu-id="f4e92-116">Es zeigt eine SPA-Anwendungsentwurf und viele der Techniken zum Erstellen einer SPA.</span><span class="sxs-lookup"><span data-stu-id="f4e92-116">It demonstrates a SPA application design and many of the techniques for building a SPA.</span></span>

<span data-ttu-id="f4e92-117">Die Kinderspiel/Knockout-Vorlage ist eine Variation auf die [KnockoutJS SPA-Vorlage](../introduction/knockoutjs-template.md) ASP.NET und Web Tools 2012.2 Update enthalten.</span><span class="sxs-lookup"><span data-stu-id="f4e92-117">The Breeze/Knockout template is a variation on the [KnockoutJS SPA template](../introduction/knockoutjs-template.md) included in the ASP.NET and Web Tools 2012.2 Update.</span></span> <span data-ttu-id="f4e92-118">Die Kinderspiel SPA-Vorlage generiert eine Anwendung mit die gleiche benutzererfahrung, verfügt aber über eine andere Implementierung, die mit Kinderspiel für die datenverwaltung.</span><span class="sxs-lookup"><span data-stu-id="f4e92-118">The Breeze SPA template generates an application with the same user experience, but it has a different implementation, using Breeze for data management.</span></span>

<span data-ttu-id="f4e92-119">Die KnockoutJS SPA-Vorlage stellt Service Requests mit unformatierten jQuery AJAX eignet sich für eine einfache Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f4e92-119">The KnockoutJS SPA template makes service requests with raw jQuery AJAX, which is adequate for a simple application.</span></span> <span data-ttu-id="f4e92-120">Jedoch höher entwickelten apps über erhöhte Anforderungen an Management-datenanforderungen.</span><span class="sxs-lookup"><span data-stu-id="f4e92-120">But more sophisticated apps have more demanding data management requirements.</span></span> <span data-ttu-id="f4e92-121">Um beispielsweise die meisten Anwendungen:</span><span class="sxs-lookup"><span data-stu-id="f4e92-121">For example, most applications:</span></span>

- <span data-ttu-id="f4e92-122">Abfragen und den Server während einer Sitzungs für erweiterte Benutzer erneut abfragen.</span><span class="sxs-lookup"><span data-stu-id="f4e92-122">Query and re-query the server during an extended user session.</span></span>
- <span data-ttu-id="f4e92-123">Fügen Sie die Abfragefiltern, Sortieren und paging.</span><span class="sxs-lookup"><span data-stu-id="f4e92-123">Add query filters, sorting, and paging.</span></span>
- <span data-ttu-id="f4e92-124">Verwenden Sie die gleichen Daten auf mehreren Bildschirmen.</span><span class="sxs-lookup"><span data-stu-id="f4e92-124">Share the same data across multiple screens.</span></span>
- <span data-ttu-id="f4e92-125">Sammeln von Änderungen auf viele Objekte, und speichern Sie diese als einzelne Transaktion.</span><span class="sxs-lookup"><span data-stu-id="f4e92-125">Accumulate changes to many objects, then save them as a single transaction.</span></span>
- <span data-ttu-id="f4e92-126">Überprüfen Sie Änderungen auf dem Client, damit der Benutzer Fehler behoben werden kann, vor dem Ausführen eines Commits für Änderungen an der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f4e92-126">Validate changes on the client, so the user can correct mistakes before committing changes to the database.</span></span>

<span data-ttu-id="f4e92-127">Die Bibliothek BreezeJS behandelt diese Arbeiten für Sie, die Sie zum Entwickeln der Anwendung Logik und die benutzerfreundlichkeit, die wichtigsten freigeben.</span><span class="sxs-lookup"><span data-stu-id="f4e92-127">The BreezeJS library handles these chores for you, freeing you to develop the application logic and user experience that matter most.</span></span>

<span data-ttu-id="f4e92-128">[**Kinderspiel** ](http://www.breezejs.com/?utm_source=ms-spa) ist eine open Source-Bibliothek zum Erstellen von umfangreichen datenanwendungen in JavaScript und HTML, die Arten von apps, die in der Vergangenheit als eigenständige desktopanwendungen übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="f4e92-128">[**Breeze**](http://www.breezejs.com/?utm_source=ms-spa) is an open source library for building rich data applications in JavaScript and HTML, the kinds of apps that have historically been delivered as stand-alone desktop applications.</span></span>

<span data-ttu-id="f4e92-129">Die Vorlage zum Kinderspiel/Knockout unterstützen Sie dieser erste entscheidenden Schritt in Richtung einer stabiler Daten Verwaltungsinfrastruktur nutzen.</span><span class="sxs-lookup"><span data-stu-id="f4e92-129">The Breeze/Knockout template helps you take that first crucial step toward a more robust data management infrastructure.</span></span> <span data-ttu-id="f4e92-130">Es erzeugt eine Todo-beispielanwendung, die mit der Vorlage KnockoutJS SPA nach außen zeigende identisch ist.</span><span class="sxs-lookup"><span data-stu-id="f4e92-130">It produces a sample Todo application that is outwardly identical to the KnockoutJS SPA template.</span></span> <span data-ttu-id="f4e92-131">Auf der Innenseite es ersetzt die AJAX-Datenschicht mit Kinderspiel, fast erreicht Seite-an-Seite, damit Sie die beiden vergleichen können.</span><span class="sxs-lookup"><span data-stu-id="f4e92-131">On the inside, it replaces the AJAX data layer with Breeze, so you can compare the two approaches side-by-side.</span></span> <span data-ttu-id="f4e92-132">Natürlich berührt es kaum das volle Potenzial von einer Anwendung zum Kinderspiel.</span><span class="sxs-lookup"><span data-stu-id="f4e92-132">Of course, it barely touches the potential of a Breeze application.</span></span> <span data-ttu-id="f4e92-133">Aber Sie sehen, wie zum Kinderspiel funktioniert und wie wenig ist erforderlich, um diesen Übergang übernehmen.</span><span class="sxs-lookup"><span data-stu-id="f4e92-133">But you'll see how Breeze works and how little is required to make that transition.</span></span>

<span data-ttu-id="f4e92-134">Fangen wir also an.</span><span class="sxs-lookup"><span data-stu-id="f4e92-134">Let's get started.</span></span>

## <a name="create-a-breezeknockout-template-project"></a><span data-ttu-id="f4e92-135">Erstellen Sie ein Kinderspiel/Knockout-Vorlagenprojekt</span><span class="sxs-lookup"><span data-stu-id="f4e92-135">Create a Breeze/Knockout Template Project</span></span>

<span data-ttu-id="f4e92-136">Herunterladen Sie und installieren Sie die Vorlage, indem Sie auf die Schaltfläche "herunterladen" oben.</span><span class="sxs-lookup"><span data-stu-id="f4e92-136">Download and install the template by clicking the Download button above.</span></span> <span data-ttu-id="f4e92-137">Die Vorlage wird als Visual Studio-Erweiterung (VSIX)-Datei verpackt.</span><span class="sxs-lookup"><span data-stu-id="f4e92-137">The template is packaged as a Visual Studio Extension (VSIX) file.</span></span> <span data-ttu-id="f4e92-138">Sie müssen möglicherweise Visual Studio neu starten.</span><span class="sxs-lookup"><span data-stu-id="f4e92-138">You might need to restart Visual Studio.</span></span>

<span data-ttu-id="f4e92-139">In der **Vorlagen** klicken Sie im Bereich **installierte Vorlagen** und erweitern Sie die **Visual C#-** Knoten.</span><span class="sxs-lookup"><span data-stu-id="f4e92-139">In the **Templates** pane, select **Installed Templates** and expand the **Visual C#** node.</span></span> <span data-ttu-id="f4e92-140">Klicken Sie unter **Visual C#-**Option **Web**.</span><span class="sxs-lookup"><span data-stu-id="f4e92-140">Under **Visual C#**, select **Web**.</span></span> <span data-ttu-id="f4e92-141">Wählen Sie in der Liste der Projektvorlagen **ASP.NET MVC 4-Webanwendung**.</span><span class="sxs-lookup"><span data-stu-id="f4e92-141">In the list of project templates, select **ASP.NET MVC 4 Web Application**.</span></span> <span data-ttu-id="f4e92-142">Nennen Sie das Projekt, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4e92-142">Name the project and click **OK**.</span></span>

<span data-ttu-id="f4e92-143">In der **neues Projekt** Assistenten **Kinderspiel Knockout SPA**.</span><span class="sxs-lookup"><span data-stu-id="f4e92-143">In the **New Project** wizard, select **Breeze Knockout SPA**.</span></span>

![](http://www.breezejs.com/sites/all/images/spa-template/SelectBreezeKOSpaTemplate.png)

<span data-ttu-id="f4e92-144">Drücken Sie STRG + F5, um zu erstellen, und führen Sie die Anwendung ohne Debuggen aus, oder drücken Sie F5, um mit Debuggen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f4e92-144">Press Ctrl-F5 to build and run the application without debugging, or press F5 to run with debugging.</span></span>

![](http://www.breezejs.com/sites/all/images/spa-template/ZephyrRunning.png)

<span data-ttu-id="f4e92-145">Wenn die Anwendung zuerst ausgeführt wird, wird einen Anmeldebildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f4e92-145">When the application first runs, it displays a login screen.</span></span> <span data-ttu-id="f4e92-146">Klicken Sie auf den Link "Registrierung", und eine neue Seite glides in der Ansicht, in dem Sie einen Benutzernamen und ein Kennwort eingeben.</span><span class="sxs-lookup"><span data-stu-id="f4e92-146">Click the "Sign up" link and a new page glides into view, where you can enter a username and password.</span></span> <span data-ttu-id="f4e92-147">(Auf die Seiten für Anmeldung und Registrierung werden über ASP.NET MVC erstellt.) Wenn Sie das Registrierungsformular übermitteln, generiert der Server eine "Todolist" mit zwei Elementen für Ihr Konto.</span><span class="sxs-lookup"><span data-stu-id="f4e92-147">(The login and registration pages are built using ASP.NET MVC.) When you submit the registration form, the server generates a TodoList with two items for your account.</span></span> <span data-ttu-id="f4e92-148">Dann stellt er diese gelben betrachtet.</span><span class="sxs-lookup"><span data-stu-id="f4e92-148">Then it presents them to you on a yellow note.</span></span>

![](http://www.breezejs.com/sites/all/images/spa-template/TodoList.png)

<span data-ttu-id="f4e92-149">Jetzt können Sie in das Land des SPA.</span><span class="sxs-lookup"><span data-stu-id="f4e92-149">Now you are in the land of SPA.</span></span> <span data-ttu-id="f4e92-150">Alles, was Sie finden Sie unter und Erfahrung beim Bearbeiten von Todos gerendert und auf dem Client mithilfe von Knockout und Kinderspiel verwaltet.</span><span class="sxs-lookup"><span data-stu-id="f4e92-150">Everything you see and experience while manipulating Todos is rendered and managed on the client with the help of Knockout and Breeze.</span></span> <span data-ttu-id="f4e92-151">Untersuchen Sie die app als Benutzer...</span><span class="sxs-lookup"><span data-stu-id="f4e92-151">Explore the app as a user …</span></span> <span data-ttu-id="f4e92-152">Dabei sollten Sie ein Entwickler.</span><span class="sxs-lookup"><span data-stu-id="f4e92-152">but with a developer's eye.</span></span> <span data-ttu-id="f4e92-153">Verwenden Sie die Developer Tools in Ihrem Browser, um den Netzwerkdatenverkehr zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="f4e92-153">Use the developer tools in your browser to capture the network traffic.</span></span> <span data-ttu-id="f4e92-154">(In InternetExplorer: Drücken Sie F12, wählen Sie die **Netzwerk** Registerkarte, und klicken Sie auf **Aufzeichnung gestartet**.) Probieren Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f4e92-154">(In Internet Explorer: Press F12, select the **Network** tab, and click **Start capturing**.) Now try the following:</span></span>

- <span data-ttu-id="f4e92-155">Fügen Sie ein neues TODO-Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="f4e92-155">Add a new Todo item.</span></span>
- <span data-ttu-id="f4e92-156">Klicken Sie auf die Bezeichnung, und bearbeiten Sie den Titel des TODO-Element</span><span class="sxs-lookup"><span data-stu-id="f4e92-156">Click the label and edit the Todo item title</span></span>
- <span data-ttu-id="f4e92-157">Kontrollkästchen Sie ein, um das Element "Fertig" ändert zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="f4e92-157">Check a checkbox to mark the item done.</span></span> <span data-ttu-id="f4e92-158">Beachten Sie, dass das Textfeld deaktiviert ist, daher ist der Titel nicht mehr bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="f4e92-158">Notice that the textbox is disabled, so the title is no longer editable.</span></span>
- <span data-ttu-id="f4e92-159">Klicken Sie auf das "X" rechts neben der Beschriftung.</span><span class="sxs-lookup"><span data-stu-id="f4e92-159">Click the ‘x' to the right of the label.</span></span> <span data-ttu-id="f4e92-160">Das Element wird nicht mehr und wird aus der Datenbank gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f4e92-160">The item disappears and is deleted from the database.</span></span>
- <span data-ttu-id="f4e92-161">Wählen Sie ein anderes Element aus, und deaktivieren Sie den Titel.</span><span class="sxs-lookup"><span data-stu-id="f4e92-161">Pick another item and clear its title.</span></span> <span data-ttu-id="f4e92-162">Sie erhalten einen Validierungsfehler, dass der Titel erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f4e92-162">You'll get a validation error that the title is required.</span></span> <span data-ttu-id="f4e92-163">Nach einer kurzen Pause wird der vorherigen Titel wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="f4e92-163">After a brief pause, the previous title is restored.</span></span>
- <span data-ttu-id="f4e92-164">Geben Sie einen übertrieben lange Titel ein.</span><span class="sxs-lookup"><span data-stu-id="f4e92-164">Type in a ridiculously long title.</span></span> <span data-ttu-id="f4e92-165">Sie erhalten einen anderen Validierungsfehler, dass der Titel zu lang ist.</span><span class="sxs-lookup"><span data-stu-id="f4e92-165">You'll get a different validation error that the title is too long.</span></span>
- <span data-ttu-id="f4e92-166">Klicken Sie auf die Schaltfläche "Hinzufügen von Todo-Liste".</span><span class="sxs-lookup"><span data-stu-id="f4e92-166">Click the "Add Todo List" button.</span></span> <span data-ttu-id="f4e92-167">Eine neue Liste, die auf der linken Seite der vorherigen Liste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f4e92-167">A new list appears to the left of the previous list.</span></span>
- <span data-ttu-id="f4e92-168">Experimentieren Sie mit der "Todolist"-Title, auslösen erforderlich und Länge Überprüfungen.</span><span class="sxs-lookup"><span data-stu-id="f4e92-168">Play with the TodoList title, triggering its required and length validations.</span></span>
- <span data-ttu-id="f4e92-169">Klicken Sie in das Textfeld Titel, deaktivieren Sie die Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f4e92-169">Click in the title textbox to clear the error message.</span></span>
- <span data-ttu-id="f4e92-170">Klicken Sie auf das "X" in der Kreis in der oberen rechten Ecke der "Todolist" und dessen Todos zu löschen.</span><span class="sxs-lookup"><span data-stu-id="f4e92-170">Click the "x" in the circle in the upper right corner to delete the TodoList and its todos.</span></span>

<span data-ttu-id="f4e92-171">Die Validierungslogik wird ausgeführt-Clientseite, indem zum Kinderspiel.</span><span class="sxs-lookup"><span data-stu-id="f4e92-171">The validation logic is performed client-side by Breeze.</span></span> <span data-ttu-id="f4e92-172">Validierungsattributen für die Server-Modell-Klassen werden an den Client weitergegeben und automatisch ausgeführt werden, bevor der Client den Server kontaktiert.</span><span class="sxs-lookup"><span data-stu-id="f4e92-172">Validation attributes on the server model classes are propagated to the client and executed automatically before the client contacts the server.</span></span>

<span data-ttu-id="f4e92-173">Überprüfen Sie den Netzwerkdatenverkehr.</span><span class="sxs-lookup"><span data-stu-id="f4e92-173">Review the network traffic.</span></span> <span data-ttu-id="f4e92-174">Beachten Sie, dass wenn Kinderspiel ein Fehler erkannt wurden keine Aufrufe an den Server.</span><span class="sxs-lookup"><span data-stu-id="f4e92-174">Notice that there were no calls to the server when Breeze detected an error.</span></span> <span data-ttu-id="f4e92-175">Jede gültige Änderung führte zu einer POST-Anforderung auf "/ api/Todo/SaveChanges".</span><span class="sxs-lookup"><span data-stu-id="f4e92-175">Each valid change resulted in a POST request to "/api/Todo/SaveChanges".</span></span> <span data-ttu-id="f4e92-176">Kinderspiel bündelt die Änderungen und sendet sie zusammen als eine einzelne Anforderung an die Web-API-Controller `SaveChanges` Methode.</span><span class="sxs-lookup"><span data-stu-id="f4e92-176">Breeze bundles the changes and sends them together as a single request to the Web API controller's `SaveChanges` method.</span></span> <span data-ttu-id="f4e92-177">Unterscheidet sich vom KockoutJS SPA-Vorlage, wodurch PUT, POST und DELETE-Anforderungen für jedes Element einzeln.</span><span class="sxs-lookup"><span data-stu-id="f4e92-177">That's different from KockoutJS SPA template, which makes PUT, POST, and DELETE requests for each item individually.</span></span>

## <a name="peek-inside"></a><span data-ttu-id="f4e92-178">Peek-in</span><span class="sxs-lookup"><span data-stu-id="f4e92-178">Peek inside</span></span>

<span data-ttu-id="f4e92-179">Diese Anwendung verfügt über eine Clientseite und einer serverseitigen.</span><span class="sxs-lookup"><span data-stu-id="f4e92-179">This application has a client side and a server side.</span></span> <span data-ttu-id="f4e92-180">Clientseitige Stapel besteht ein wenig HTML und eine Kombination aus JavaScript Anwendungsmodulen (im Ordner "app") plus Drittanbieter-JavaScript-Bibliotheken (im Ordner "Skripts").</span><span class="sxs-lookup"><span data-stu-id="f4e92-180">The client-side stack consists of a little HTML and a combination of application JavaScript modules (in the "app" folder) plus third-party JavaScript libraries (in the "Scripts" folder).</span></span>

![](http://www.breezejs.com/sites/all/images/spa-template/ClientArchitecture.png)

<span data-ttu-id="f4e92-181">Wenn Sie die Vorlage KnockoutJS SPA untersucht haben, sollte dies sehr bekannt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="f4e92-181">If you've investigated the KnockoutJS SPA template, this should look very familiar.</span></span> <span data-ttu-id="f4e92-182">Konzentrieren Sie sich auf den blauen Feldern.</span><span class="sxs-lookup"><span data-stu-id="f4e92-182">Focus on the blue boxes.</span></span> <span data-ttu-id="f4e92-183">Die UI-Architektur ist Model-View-ViewModel (MVVM), in dem die HTML-Widgets der Sicht aus dem unterstützenden Presentation-Code in das Ansichtsmodell ordnungsgemäß getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="f4e92-183">The UI architecture is Model-View-ViewModel (MVVM), in which the HTML widgets of the view are cleanly separated from the supporting presentation code in the view-model.</span></span> <span data-ttu-id="f4e92-184">Ein Daten-Bindungssystem (in diesem Fall Knockout) koordiniert die Ansicht und das Modell anzeigen, sodass jeder ohne fundierte Kenntnisse der anderen Fehlerereignissen kann.</span><span class="sxs-lookup"><span data-stu-id="f4e92-184">A data binding system (Knockout in this case) coordinates the view and view-model so that each can do its job without intimate knowledge of the other.</span></span>

<span data-ttu-id="f4e92-185">Das Modell kapselt die TODO-Daten.</span><span class="sxs-lookup"><span data-stu-id="f4e92-185">The model encapsulates the Todo data.</span></span> <span data-ttu-id="f4e92-186">Entitäten im Modell werden erstellt, indem Kinderspiel mit Knockout Observable-Eigenschaften, damit sie direkt an Widgets in der Ansicht gebunden werden können.</span><span class="sxs-lookup"><span data-stu-id="f4e92-186">Entities in the model are constructed by Breeze with Knockout observable properties, so they can be bound directly to widgets in the view.</span></span> <span data-ttu-id="f4e92-187">Das Ansichtsmodell fragt den Datenkontext zum Abrufen und speichern die Modellelemente.</span><span class="sxs-lookup"><span data-stu-id="f4e92-187">The view-model asks the data context to acquire and save the model entities.</span></span> <span data-ttu-id="f4e92-188">Der Datenkontext für Netzwerkgeräte delegiert die meiste Arbeit zum Kinderspiel.</span><span class="sxs-lookup"><span data-stu-id="f4e92-188">The data context delegates most of the work to Breeze.</span></span>

<span data-ttu-id="f4e92-189">Serverseitige Stapel besteht aus einigen Entwicklercode und drei Prinzip .NET Bibliotheken: Web-API und Entity Framework Breeze.NET:</span><span class="sxs-lookup"><span data-stu-id="f4e92-189">The server-side stack consists of some developer code and three principle .NET libraries: Web API, Entity Framework, and Breeze.NET:</span></span>

![](http://www.breezejs.com/sites/all/images/spa-template/ServerArchitecture.png)

<span data-ttu-id="f4e92-190">Die grundlegende Architektur ist identisch mit der KockoutJS SPA-Vorlage.</span><span class="sxs-lookup"><span data-stu-id="f4e92-190">The basic architecture is the same as the KockoutJS SPA template.</span></span> <span data-ttu-id="f4e92-191">Die Implementierung ist jedoch viel einfacher: der DTOs gelöscht wurden, und die meisten Details Entity Framework haben Breeze.NET zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="f4e92-191">However, the implementation is much simpler: The DTOs were deleted, and most of the Entity Framework details have been delegated to Breeze.NET.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f4e92-192">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f4e92-192">Next Steps</span></span>

<span data-ttu-id="f4e92-193">Es wird empfohlen, Sie den Code untersuchen, durch MDX die [umfassende Erläuterung](http://www.breezejs.com/spa-template?utm_source=ms-spa) des Clients und der Server-Stapel auf der Website zum Kinderspiel.</span><span class="sxs-lookup"><span data-stu-id="f4e92-193">We suggest that you explore the code, guided by the [extensive discussion](http://www.breezejs.com/spa-template?utm_source=ms-spa) of both the client and the server stacks on the Breeze website.</span></span>

<span data-ttu-id="f4e92-194">Sie könnten versuchen, arbeiten mit Kinderspiel clientseitige Abfrage; Fügen Sie einige Filter und sortiert.</span><span class="sxs-lookup"><span data-stu-id="f4e92-194">You might try playing with Breeze client-side query; add some filters and sorts.</span></span> <span data-ttu-id="f4e92-195">Sie können weitere Modelleigenschaften und weitere Entitäten an, die eine bessere Gefühl für die End-to-End-SPA Entwicklung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f4e92-195">You might add more model properties and more entities to get a better feel for end-to-end SPA development.</span></span> <span data-ttu-id="f4e92-196">Wenn Sie den Entwurf sicher sind, können Sie TODO-Funktionen entfernen und Ersetzen Sie sie durch Ihren eigenen.</span><span class="sxs-lookup"><span data-stu-id="f4e92-196">When you are confident of the design, you can tear out the Todo features and replace them with your own.</span></span>

<span data-ttu-id="f4e92-197">Bereit für Nächstes big bald verlaufen: Hinzufügen von clientseitigen Bildschirme und zwischen ihnen navigieren.</span><span class="sxs-lookup"><span data-stu-id="f4e92-197">Soon you'll be ready for the next big step: Adding client-side screens and navigating among them.</span></span> <span data-ttu-id="f4e92-198">Sie diese Vorlage SPA hinterlassen und aktivieren Sie auf eine umfassendere SPA-Stapel, z. B. [John-Papa Hot Handtuch](https://github.com/johnpapa/HotTowel#readme "Hot Handtuch"), die Durandal aus der Mischung Kinderspiel und Knockout hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="f4e92-198">You'll leave this SPA template behind and turn to a more complete SPA stack, such as [John Papa's Hot Towel](https://github.com/johnpapa/HotTowel#readme "Hot Towel"), which adds Durandal to the Breeze and Knockout mix.</span></span>