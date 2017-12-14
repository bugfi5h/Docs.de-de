---
uid: signalr/overview/getting-started/introduction-to-signalr
title: "Einführung in SignalR | Microsoft Docs"
author: pfletcher
description: "In diesem Artikel wird beschrieben, was eine SignalR ist und einige der Lösungen, die dieser Standard entwickelt wurde, um zu erstellen."
ms.author: aspnetcontent
manager: wpickett
ms.date: 06/10/2014
ms.topic: article
ms.assetid: 0fab5e35-8c1f-43d4-8635-b8aba8766a71
ms.technology: dotnet-signalr
ms.prod: .net-framework
msc.legacyurl: /signalr/overview/getting-started/introduction-to-signalr
msc.type: authoredcontent
ms.openlocfilehash: 27150d314b6861f1098e6ef4a7de94e7b371a78e
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2017
---
<a name="introduction-to-signalr"></a><span data-ttu-id="aa5b2-103">Einführung in SignalR</span><span class="sxs-lookup"><span data-stu-id="aa5b2-103">Introduction to SignalR</span></span>
====================
<span data-ttu-id="aa5b2-104">durch [Patrick Fletcher](https://github.com/pfletcher)</span><span class="sxs-lookup"><span data-stu-id="aa5b2-104">by [Patrick Fletcher](https://github.com/pfletcher)</span></span>

> <span data-ttu-id="aa5b2-105">In diesem Artikel wird beschrieben, was eine SignalR ist und einige der Lösungen, die dieser Standard entwickelt wurde, um zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-105">This article describes what SignalR is, and some of the solutions it was designed to create.</span></span> 
> 
> ## <a name="questions-and-comments"></a><span data-ttu-id="aa5b2-106">Fragen und Kommentare</span><span class="sxs-lookup"><span data-stu-id="aa5b2-106">Questions and comments</span></span>
> 
> <span data-ttu-id="aa5b2-107">Lassen Sie Sie Feedback auf wie in diesem Lernprogramm mögen und was wir in den Kommentaren am unteren Rand der Seite verbessern können.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-107">Please leave feedback on how you liked this tutorial and what we could improve in the comments at the bottom of the page.</span></span> <span data-ttu-id="aa5b2-108">Wenn Sie Fragen, die nicht direkt mit dem Lernprogramm verknüpft sind haben, bereitstellen können, die [ASP.NET SignalR-Forum](https://forums.asp.net/1254.aspx/1?ASP+NET+SignalR) oder [StackOverflow.com](http://stackoverflow.com/).</span><span class="sxs-lookup"><span data-stu-id="aa5b2-108">If you have questions that are not directly related to the tutorial, you can post them to the [ASP.NET SignalR forum](https://forums.asp.net/1254.aspx/1?ASP+NET+SignalR) or [StackOverflow.com](http://stackoverflow.com/).</span></span>


## <a name="what-is-signalr"></a><span data-ttu-id="aa5b2-109">Was eine SignalR ist?</span><span class="sxs-lookup"><span data-stu-id="aa5b2-109">What is SignalR?</span></span>

<span data-ttu-id="aa5b2-110">ASP.NET SignalR ist eine Bibliothek für ASP.NET-Entwickler,, die den Prozess des Hinzufügens von Echtzeit-Webfunktionen zu Anwendungen vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-110">ASP.NET SignalR is a library for ASP.NET developers that simplifies the process of adding real-time web functionality to applications.</span></span> <span data-ttu-id="aa5b2-111">Echtzeit-Webfunktionen ist die Möglichkeit, Server Code Inhalte mithilfe von Push sofort an verbundene Clients sobald sie verfügbar sind, statt den Server für einen Client zum Anfordern von neuer Daten warten.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-111">Real-time web functionality is the ability to have server code push content to connected clients instantly as it becomes available, rather than having the server wait for a client to request new data.</span></span>

<span data-ttu-id="aa5b2-112">SignalR kann verwendet werden, Ihre ASP.NET-Anwendung jegliche Art von "in Echtzeit"-Webfunktionen hinzu.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-112">SignalR can be used to add any sort of "real-time" web functionality to your ASP.NET application.</span></span> <span data-ttu-id="aa5b2-113">Während der Chat häufig als Beispiel verwendet wird, können Sie viel mehr tun.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-113">While chat is often used as an example, you can do a whole lot more.</span></span> <span data-ttu-id="aa5b2-114">Jedes Mal ein Benutzer aktualisiert eine Webseite, um neue Daten anzuzeigen, oder die Seite implementiert [lange](http://en.wikipedia.org/wiki/Push_technology#Long_polling) um neue Daten abzurufen, ist es ein Kandidat für die Verwendung von SignalR.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-114">Any time a user refreshes a web page to see new data, or the page implements [long polling](http://en.wikipedia.org/wiki/Push_technology#Long_polling) to retrieve new data, it is a candidate for using SignalR.</span></span> <span data-ttu-id="aa5b2-115">Beispiele für Dashboards und Überwachen von Anwendungen, die Anwendungen (z. B. die gleichzeitige Bearbeitung von Dokumenten), für die Zusammenarbeit Auftrag Statusupdates und Formulare in Echtzeit.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-115">Examples include dashboards and monitoring applications, collaborative applications (such as simultaneous editing of documents), job progress updates, and real-time forms.</span></span>

<span data-ttu-id="aa5b2-116">SignalR ermöglicht auch völlig neue Arten von Webanwendungen, die sehr häufig Updates vom Server, erfordern z. B. Echtzeit spielen.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-116">SignalR also enables completely new types of web applications that require high frequency updates from the server, for example, real-time gaming.</span></span> <span data-ttu-id="aa5b2-117">Ein hervorragendes Beispiel hierfür finden Sie unter der [ShootR Spiel.](http://shootr.signalr.net/)</span><span class="sxs-lookup"><span data-stu-id="aa5b2-117">For a great example of this, see the [ShootR game.](http://shootr.signalr.net/)</span></span>

<span data-ttu-id="aa5b2-118">SignalR stellt eine einfache API zum Erstellen von Server-zu-Client von Remoteprozeduraufrufen (RPC), die JavaScript-Funktionen im Client Browsern (und andere Clientplattformen) vom serverseitigen .NET Code aufrufen.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-118">SignalR provides a simple API for creating server-to-client remote procedure calls (RPC) that call JavaScript functions in client browsers (and other client platforms) from server-side .NET code.</span></span> <span data-ttu-id="aa5b2-119">SignalR enthält außerdem eine API für die verbindungsverwaltung (z. B. eine Verbindung herstellen, und Ereignisse zum Trennen), und Gruppieren von Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-119">SignalR also includes API for connection management (for instance, connect and disconnect events), and grouping connections.</span></span>

![Aufrufen von Methoden mit SignalR](introduction-to-signalr/_static/image1.png)

<span data-ttu-id="aa5b2-121">SignalR verbindungsverwaltung automatisch behandelt, und Ihnen Broadcastmeldungen für alle verbundenen Clients gleichzeitig, z. B. einem Chatraum.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-121">SignalR handles connection management automatically, and lets you broadcast messages to all connected clients simultaneously, like a chat room.</span></span> <span data-ttu-id="aa5b2-122">Sie können auch Nachrichten für bestimmte Clients senden.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-122">You can also send messages to specific clients.</span></span> <span data-ttu-id="aa5b2-123">Die Verbindung zwischen Client und Server ist persistent, im Gegensatz zu einer klassischen HTTP-Verbindung, die für die einzelnen mitteillungen wieder hergestellt ist.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-123">The connection between the client and server is persistent, unlike a classic HTTP connection, which is re-established for each communication.</span></span>

<span data-ttu-id="aa5b2-124">SignalR unterstützt "Serverpush"-Funktionalität, die in der Servercode Clientcode in der Browser über Remote Procedure Calls (RPC), statt über allgemeine Anforderung / Antwort-Modell im Web heute aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-124">SignalR supports "server push" functionality, in which server code can call out to client code in the browser using Remote Procedure Calls (RPC), rather than the request-response model common on the web today.</span></span>

<span data-ttu-id="aa5b2-125">SignalR-Anwendungen können Tausende von Clients mithilfe von Service Bus, SQL Server horizontal oder [Redis](http://redis.io).</span><span class="sxs-lookup"><span data-stu-id="aa5b2-125">SignalR applications can scale out to thousands of clients using Service Bus, SQL Server or [Redis](http://redis.io).</span></span>

<span data-ttu-id="aa5b2-126">SignalR ist Open Source, über [GitHub](https://github.com/signalr).</span><span class="sxs-lookup"><span data-stu-id="aa5b2-126">SignalR is open-source, accessible through [GitHub](https://github.com/signalr).</span></span>

## <a name="signalr-and-websocket"></a><span data-ttu-id="aa5b2-127">SignalR und WebSocket</span><span class="sxs-lookup"><span data-stu-id="aa5b2-127">SignalR and WebSocket</span></span>

<span data-ttu-id="aa5b2-128">SignalR wird der neue WebSocket-Transport verwendet, sofern verfügbar, und Sie auf ältere Transporte zurückgegriffen, wenn nötig.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-128">SignalR uses the new WebSocket transport where available, and falls back to older transports where necessary.</span></span> <span data-ttu-id="aa5b2-129">Während Sie sicherlich schreiben, können Ihre Anwendung direkt mit dem WebSocket, mithilfe von SignalR-Mitteln, die ein Großteil der zusätzliche Funktionalität, die Sie implementieren müssten Sie durchgeführt haben wird.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-129">While you could certainly write your application using WebSocket directly, using SignalR means that a lot of the extra functionality you would need to implement will already have been done for you.</span></span> <span data-ttu-id="aa5b2-130">Am wichtigsten ist, bedeutet dies, dass Sie Ihre Anwendung WebSocket nutzen, ohne dass Gedanken machen, erstellen einen separaten Codepfad für ältere Clients schreiben können.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-130">Most importantly, this means that you can code your application to take advantage of WebSocket without having to worry about creating a separate code path for older clients.</span></span> <span data-ttu-id="aa5b2-131">SignalR schützt auch vom Vorhandensein Updates WebSocket, kümmern, da weiterhin aktualisiert werden, um die Änderungen in den zugrunde liegenden Transport unterstützen SignalR Ihrer Anwendung eine konsistente Schnittstelle zwischen Versionen der WebSocket bereit.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-131">SignalR also shields you from having to worry about updates to WebSocket, since SignalR will continue to be updated to support changes in the underlying transport, providing your application a consistent interface across versions of WebSocket.</span></span>

<span data-ttu-id="aa5b2-132">Während Sie eine Lösung mit WebSocket allein sicherlich erstellen können, bietet SignalR alle Funktionen, die Sie selbst, z. B. Fallback auf andere Transporte und Überarbeiten die Anwendung für Updates WebSocket-Implementierungen schreiben müssen.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-132">While you could certainly create a solution using WebSocket alone, SignalR provides all of the functionality you would need to write yourself, such as fallback to other transports and revising your application for updates to WebSocket implementations.</span></span>

<a id="transports"></a>

## <a name="transports-and-fallbacks"></a><span data-ttu-id="aa5b2-133">Transporte und Zugriffe</span><span class="sxs-lookup"><span data-stu-id="aa5b2-133">Transports and fallbacks</span></span>

<span data-ttu-id="aa5b2-134">SignalR ist eine Abstraktion über einige der verwendete Transporte, die in Echtzeit Arbeit zwischen Client und Server erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-134">SignalR is an abstraction over some of the transports that are required to do real-time work between client and server.</span></span> <span data-ttu-id="aa5b2-135">Eine SignalR-Verbindung HTTP startet und wird dann um eine WebSocket-Verbindung heraufgestuft, sofern dieser verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-135">A SignalR connection starts as HTTP, and is then promoted to a WebSocket connection if it is available.</span></span> <span data-ttu-id="aa5b2-136">WebSocket ist der idealen Transport für SignalR, da es macht die effizienteste Nutzung des Serverspeichers, hat die niedrigste Latenz und verfügt über die meisten zugrunde liegenden Funktionen (z. B. Vollduplex-Kommunikation zwischen Client und Server), aber sie auch den strengsten hat Anforderungen: WebSocket der Server mit Windows Server 2012 oder Windows 8 und .NET Framework 4.5 werden muss.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-136">WebSocket is the ideal transport for SignalR, since it makes the most efficient use of server memory, has the lowest latency, and has the most underlying features (such as full duplex communication between client and server), but it also has the most stringent requirements: WebSocket requires the server to be using Windows Server 2012 or Windows 8, and .NET Framework 4.5.</span></span> <span data-ttu-id="aa5b2-137">Wenn diese Anforderungen nicht erfüllt sind, versucht SignalR andere Transporte verwenden, um dessen Verbindungen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-137">If these requirements are not met, SignalR will attempt to use other transports to make its connections.</span></span>

### <a name="html-5-transports"></a><span data-ttu-id="aa5b2-138">HTML 5-Transporte</span><span class="sxs-lookup"><span data-stu-id="aa5b2-138">HTML 5 transports</span></span>

<span data-ttu-id="aa5b2-139">Diese Transporte richten sich nach Unterstützung für [HTML 5](http://en.wikipedia.org/wiki/HTML5).</span><span class="sxs-lookup"><span data-stu-id="aa5b2-139">These transports depend on support for [HTML 5](http://en.wikipedia.org/wiki/HTML5).</span></span> <span data-ttu-id="aa5b2-140">Wenn der Clientbrowser HTML 5-Standard nicht unterstützt, werden ältere Transporte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-140">If the client browser does not support the HTML 5 standard, older transports will be used.</span></span>

- <span data-ttu-id="aa5b2-141">**WebSocket** (wenn die dem Server und dem Browser anzugeben, können sie die Websocket unterstützen).</span><span class="sxs-lookup"><span data-stu-id="aa5b2-141">**WebSocket** (if the both the server and browser indicate they can support Websocket).</span></span> <span data-ttu-id="aa5b2-142">WebSocket ist die einzige Transport, der eine "true" persistente, bidirektionale Verbindung zwischen Client und Server hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-142">WebSocket is the only transport that establishes a true persistent, two-way connection between client and server.</span></span> <span data-ttu-id="aa5b2-143">Allerdings gelten WebSocket auch strengsten; Es wird nur in den neuesten Versionen von Microsoft Internet Explorer und Google Chrome, Mozilla Firefox vollständig unterstützt, und nur partielle Implementierung hat, in anderen Browsern, z. B. Opera und Safari.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-143">However, WebSocket also has the most stringent requirements; it is fully supported only in the latest versions of Microsoft Internet Explorer, Google Chrome, and Mozilla Firefox, and only has a partial implementation in other browsers such as Opera and Safari.</span></span>
- <span data-ttu-id="aa5b2-144">**Server gesendete Ereignisse**, auch bekannt als EventSource (wenn der Browser Server gesendete Ereignisse, die im Grunde wird von allen Browsern mit Ausnahme von Internet Explorer unterstützt.)</span><span class="sxs-lookup"><span data-stu-id="aa5b2-144">**Server Sent Events**, also known as EventSource (if the browser supports Server Sent Events, which is basically all browsers except Internet Explorer.)</span></span>

### <a name="comet-transports"></a><span data-ttu-id="aa5b2-145">Comet-Transporte</span><span class="sxs-lookup"><span data-stu-id="aa5b2-145">Comet transports</span></span>

<span data-ttu-id="aa5b2-146">Die folgenden Transportoptionen basieren auf der [Comet](http://en.wikipedia.org/wiki/Comet_(programming)) webanwendungsmodells, in der ein Browser oder einem anderen Client eine lang aufrechterhalten HTTP-Anforderung, die der Server verwenden kann beibehält, insbesondere Daten an den Client ohne den Client pushen soll Sie anfordern.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-146">The following transports are based on the [Comet](http://en.wikipedia.org/wiki/Comet_(programming)) web application model, in which a browser or other client maintains a long-held HTTP request, which the server can use to push data to the client without the client specifically requesting it.</span></span>

- <span data-ttu-id="aa5b2-147">**Forever Frame** (für nur in Internet Explorer).</span><span class="sxs-lookup"><span data-stu-id="aa5b2-147">**Forever Frame** (for Internet Explorer only).</span></span> <span data-ttu-id="aa5b2-148">Unbegrenzte erstellt Frame ein versteckten IFRAMEs, wodurch eine Anforderung an einen Endpunkt auf dem Server, die nicht abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-148">Forever Frame creates a hidden IFrame which makes a request to an endpoint on the server that does not complete.</span></span> <span data-ttu-id="aa5b2-149">Der Server sendet dann fortlaufend Skript an den Client die sofort ausgeführt wird, stellt eine unidirektionale Echtzeit-Verbindung vom Server an Client.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-149">The server then continually sends script to the client which is immediately executed, providing a one-way realtime connection from server to client.</span></span> <span data-ttu-id="aa5b2-150">Die Verbindung vom Client zum Server verwendet eine separate Verbindung vom Server zu Clientverbindung, und wie eine standard-HTTP-Anforderung eine neue Verbindung erstellt wird, für jedes Datenelement, die gesendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-150">The connection from client to server uses a separate connection from the server to client connection, and like a standard HTTP request, a new connection is created for each piece of data that needs to be sent.</span></span>
- <span data-ttu-id="aa5b2-151">**Lange abrufen AJAX**.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-151">**Ajax long polling**.</span></span> <span data-ttu-id="aa5b2-152">Langes Abrufintervall erstellt keine dauerhafte Verbindung jedoch stattdessen fragt den Server mit einer Anforderung, die geöffnet bleibt, bis der Server antwortet, an welchem Punkt die Verbindung wird geschlossen, und eine neue Verbindung sofort angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-152">Long polling does not create a persistent connection, but instead polls the server with a request that stays open until the server responds, at which point the connection closes, and a new connection is requested immediately.</span></span> <span data-ttu-id="aa5b2-153">Dies kann einige Latenz führen, während die Verbindung zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-153">This may introduce some latency while the connection resets.</span></span>

<span data-ttu-id="aa5b2-154">Weitere Informationen, welche Transporte unter welche Konfigurationen unterstützt werden, finden Sie unter [unterstützte Plattformen](supported-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="aa5b2-154">For more information on what transports are supported under which configurations, see [Supported Platforms](supported-platforms.md).</span></span>

### <a name="transport-selection-process"></a><span data-ttu-id="aa5b2-155">Transport Auswahlprozesses verwendet werden</span><span class="sxs-lookup"><span data-stu-id="aa5b2-155">Transport selection process</span></span>

<span data-ttu-id="aa5b2-156">Die folgende Liste enthält die Schritte, die SignalR verwendet, um zu entscheiden, welcher transport.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-156">The following list shows the steps that SignalR uses to decide which transport to use.</span></span>

1. <span data-ttu-id="aa5b2-157">Wenn der Browser InternetExplorer 8 oder niedriger ist, wird die langen Abfragen verwendet.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-157">If the browser is Internet Explorer 8 or earlier, Long Polling is used.</span></span>
2. <span data-ttu-id="aa5b2-158">Wenn JSONP konfiguriert ist (d. h. die `jsonp` Parameter auf festgelegt ist `true` Wenn die Verbindung gestartet ist), lange Abruf verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-158">If JSONP is configured (that is, the `jsonp` parameter is set to `true` when the connection is started), Long Polling is used.</span></span>
3. <span data-ttu-id="aa5b2-159">Wenn eine domänenübergreifende-Verbindung hergestellt wird (d. h., wenn der SignalR-Endpunkt nicht in derselben Domäne wie der Hostseite ist), wird WebSocket verwendet werden, wenn die folgenden Kriterien erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="aa5b2-159">If a cross-domain connection is being made (that is, if the SignalR endpoint is not in the same domain as the hosting page), then WebSocket will be used if the following criteria are met:</span></span>

    - <span data-ttu-id="aa5b2-160">Der Client unterstützt die CORS (Cross-Origin Resource Sharing).</span><span class="sxs-lookup"><span data-stu-id="aa5b2-160">The client supports CORS (Cross-Origin Resource Sharing).</span></span> <span data-ttu-id="aa5b2-161">Details zu den Clients CORS unterstützen, finden Sie unter [CORS am caniuse.com](http://www.caniuse.com/CORS).</span><span class="sxs-lookup"><span data-stu-id="aa5b2-161">For details on which clients support CORS, see [CORS at caniuse.com](http://www.caniuse.com/CORS).</span></span>
    - <span data-ttu-id="aa5b2-162">Der Client unterstützt WebSocket</span><span class="sxs-lookup"><span data-stu-id="aa5b2-162">The client supports WebSocket</span></span>
    - <span data-ttu-id="aa5b2-163">Der Server unterstützt WebSocket</span><span class="sxs-lookup"><span data-stu-id="aa5b2-163">The server supports WebSocket</span></span>

    <span data-ttu-id="aa5b2-164">Wenn keines diese Kriterien nicht erfüllt sind, wird die langen Abfragen verwendet.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-164">If any of these criteria are not met, Long Polling will be used.</span></span> <span data-ttu-id="aa5b2-165">Weitere Informationen für domänenübergreifende Verbindungen finden Sie unter [Gewusst wie: Herstellen einer Verbindung domänenübergreifende](../guide-to-the-api/hubs-api-guide-javascript-client.md#crossdomain).</span><span class="sxs-lookup"><span data-stu-id="aa5b2-165">For more information on cross-domain connections, see [How to establish a cross-domain connection](../guide-to-the-api/hubs-api-guide-javascript-client.md#crossdomain).</span></span>
4. <span data-ttu-id="aa5b2-166">Wenn JSONP ist nicht konfiguriert, und die Verbindung keine domänenübergreifende ist, werden WebSocket verwendet werden, wenn Client und Server unterstützen.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-166">If JSONP is not configured and the connection is not cross-domain, WebSocket will be used if both the client and server support it.</span></span>
5. <span data-ttu-id="aa5b2-167">Wenn der Client oder Server WebSocket nicht unterstützt wird, wird Server gesendete Ereignisse verwendet, sofern dieser verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-167">If either the client or server do not support WebSocket, Server Sent Events is used if it is available.</span></span>
6. <span data-ttu-id="aa5b2-168">Wenn Server gesendete Ereignisse nicht verfügbar ist, wird eine unbegrenzte Zeitdauer aufbewahrt Frame versucht.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-168">If Server Sent Events is not available, Forever Frame is attempted.</span></span>
7. <span data-ttu-id="aa5b2-169">Wenn Forever Frame ein Fehler auftritt, wird die langen Abfragen verwendet.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-169">If Forever Frame fails, Long Polling is used.</span></span>

<a id="MonitoringTransports"></a>
### <a name="monitoring-transports"></a><span data-ttu-id="aa5b2-170">Überwachung von Transporten</span><span class="sxs-lookup"><span data-stu-id="aa5b2-170">Monitoring transports</span></span>

<span data-ttu-id="aa5b2-171">Sie können bestimmen, welcher Transport Ihrer Anwendung verwendet wird, durch Aktivieren der Protokollierung für Ihren Hub, und öffnen das Konsolenfenster in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-171">You can determine what transport your application is using by enabling logging on your hub, and opening the console window in your browser.</span></span>

<span data-ttu-id="aa5b2-172">Fügen Sie den folgenden Befehl zum Aktivieren der Protokollierung für Ihren Hub-Ereignisse in einem Browser an die Clientanwendung:</span><span class="sxs-lookup"><span data-stu-id="aa5b2-172">To enable logging for your hub's events in a browser, add the following command to your client application:</span></span>

`$.connection.hub.logging = true;`

- <span data-ttu-id="aa5b2-173">Klicken Sie in Internet Explorer öffnen Sie der Entwicklertools durch Drücken von F12, und klicken Sie auf der Registerkarte "Console".</span><span class="sxs-lookup"><span data-stu-id="aa5b2-173">In Internet Explorer, open the developer tools by pressing F12, and click the Console tab.</span></span>

    ![-Konsole in Microsoft Internet Explorer](introduction-to-signalr/_static/image2.png)
- <span data-ttu-id="aa5b2-175">Öffnen Sie die Konsole in Chrome durch Drücken von STRG + UMSCHALT + J.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-175">In Chrome, open the console by pressing Ctrl+Shift+J.</span></span>

    ![-Konsole im Google Chrome](introduction-to-signalr/_static/image3.png)

<span data-ttu-id="aa5b2-177">Die Konsole öffnen und die Protokollierung aktiviert müssen Sie möglicherweise finden Sie unter welcher Transport von SignalR verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-177">With the console open and logging enabled, you'll be able to see which transport is being used by SignalR.</span></span>

![In Internet Explorer mit der WebSocket-Transport-Konsole](introduction-to-signalr/_static/image4.png)

### <a name="specifying-a-transport"></a><span data-ttu-id="aa5b2-179">Angeben eines Transports</span><span class="sxs-lookup"><span data-stu-id="aa5b2-179">Specifying a transport</span></span>

<span data-ttu-id="aa5b2-180">Aushandeln der Transport hat eine bestimmte Menge an Zeit und Client/Server-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-180">Negotiating a transport takes a certain amount of time and client/server resources.</span></span> <span data-ttu-id="aa5b2-181">Wenn Sie die Clientfunktionen bekannt sind, kann ein Transport angegeben werden, wenn die Clientverbindung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-181">If the client capabilities are known, then a transport can be specified when the client connection is started.</span></span> <span data-ttu-id="aa5b2-182">Der folgende Codeausschnitt veranschaulicht, starten eine Verbindung über den Transport Ajax lange abrufen, das verwendet werden würde, wenn bekannt war, dass der Client ein anderes Protokoll nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="aa5b2-182">The following code snippet demonstrates starting a connection using the Ajax Long Polling transport, as would be used if it was known that the client did not support any other protocol:</span></span>

`connection.start({ transport: 'longPolling' });`

<span data-ttu-id="aa5b2-183">Sie können eine fallback-Reihenfolge angeben, wenn einen Client bestimmte Transporte in der Reihenfolge versuchen soll.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-183">You can specify a fallback order if you want a client to try specific transports in order.</span></span> <span data-ttu-id="aa5b2-184">Der folgende Codeausschnitt veranschaulicht beim WebSocket und, die fehlschlagen, navigieren Sie direkt zu lange abrufen.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-184">The following code snippet demonstrates trying WebSocket, and failing that, going directly to Long Polling.</span></span>

`connection.start({ transport: ['webSockets','longPolling'] });`

<span data-ttu-id="aa5b2-185">Zeichenfolgenkonstanten zum Angeben von Transporten sind folgendermaßen definiert:</span><span class="sxs-lookup"><span data-stu-id="aa5b2-185">The string constants for specifying transports are defined as follows:</span></span>

- `webSockets`
- `foreverFrame`
- `serverSentEvents`
- `longPolling`

## <a name="connections-and-hubs"></a><span data-ttu-id="aa5b2-186">Verbindungen und-Hubs</span><span class="sxs-lookup"><span data-stu-id="aa5b2-186">Connections and Hubs</span></span>

<span data-ttu-id="aa5b2-187">Die SignalR-API enthält zwei Modelle für die Kommunikation zwischen Clients und Server: dauerhafte Verbindungen und Hubs.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-187">The SignalR API contains two models for communicating between clients and servers: Persistent Connections and Hubs.</span></span>

<span data-ttu-id="aa5b2-188">Eine Verbindung stellt einen einfachen Endpunkt für die einzelnen Empfänger, gruppierter oder broadcast Senden von Nachrichten dar.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-188">A Connection represents a simple endpoint for sending single-recipient, grouped, or broadcast messages.</span></span> <span data-ttu-id="aa5b2-189">Die dauerhafte Verbindung-API (in .NET Code von der Klasse "persistentconnection" dargestellt) ermöglicht es der Entwickler direkten Zugriff auf die SignalR stellt Low-Level-Kommunikationsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-189">The Persistent Connection API (represented in .NET code by the PersistentConnection class) gives the developer direct access to the low-level communication protocol that SignalR exposes.</span></span> <span data-ttu-id="aa5b2-190">Mit den Verbindungen Kommunikationsmodell werden-Entwicklern vertraut, die Verbindung basierende APIs wie z. B. Windows Communication Foundation verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-190">Using the Connections communication model will be familiar to developers who have used connection-based APIs such as Windows Communication Foundation.</span></span>

<span data-ttu-id="aa5b2-191">Ein Hub ist eine grobe Pipeline, die auf den Verbindungs-API, die der Client-als auch direkt aufrufen von Methoden voneinander ermöglicht basiert.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-191">A Hub is a more high-level pipeline built upon the Connection API that allows your client and server to call methods on each other directly.</span></span> <span data-ttu-id="aa5b2-192">SignalR übernimmt die die Verteilung über Computergrenzen hinweg wie durch Magic, sodass Clients zum Aufrufen von Methoden auf dem Server als einfach als lokalen Methoden (und umgekehrt).</span><span class="sxs-lookup"><span data-stu-id="aa5b2-192">SignalR handles the dispatching across machine boundaries as if by magic, allowing clients to call methods on the server as easily as local methods, and vice versa.</span></span> <span data-ttu-id="aa5b2-193">Mithilfe der Hubs Kommunikationsmodell werden-Entwicklern vertraut, die Remoteaufruf APIs wie .NET Remoting verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-193">Using the Hubs communication model will be familiar to developers who have used remote invocation APIs such as .NET Remoting.</span></span> <span data-ttu-id="aa5b2-194">Mit einem Hub können Sie auch stark typisierte Parameter an die Methoden, wurden die modellbindung ermöglichen übergeben.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-194">Using a Hub also allows you to pass strongly typed parameters to methods, enabling model binding.</span></span>

### <a name="architecture-diagram"></a><span data-ttu-id="aa5b2-195">Architekturdiagramm</span><span class="sxs-lookup"><span data-stu-id="aa5b2-195">Architecture diagram</span></span>

<span data-ttu-id="aa5b2-196">Das folgende Diagramm zeigt die Beziehung zwischen Hubs, permanente Verbindungen und den zugrunde liegenden Technologien für Transporte verwendet.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-196">The following diagram shows the relationship between Hubs, Persistent Connections, and the underlying technologies used for transports.</span></span>

![SignalR-Architekturdiagramm, die mit APIs, Transporte und clients](introduction-to-signalr/_static/image5.png)

### <a name="how-hubs-work"></a><span data-ttu-id="aa5b2-198">Funktionsweise von Hubs</span><span class="sxs-lookup"><span data-stu-id="aa5b2-198">How Hubs work</span></span>

<span data-ttu-id="aa5b2-199">Bei der serverseitigen Code auf dem Client eine Methode aufruft, wird ein Paket gesendet, in der aktive Transport, der den Namen und den Parametern der aufzurufenden Methode enthält (wenn ein Objekt als Parameter der Methode gesendet wird, wird es serialisiert mit JSON).</span><span class="sxs-lookup"><span data-stu-id="aa5b2-199">When server-side code calls a method on the client, a packet is sent across the active transport that contains the name and parameters of the method to be called (when an object is sent as a method parameter, it is serialized using JSON).</span></span> <span data-ttu-id="aa5b2-200">Der Client vergleicht dann den Methodennamen an Methoden, die im clientseitigen Code definiert.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-200">The client then matches the method name to methods defined in client-side code.</span></span> <span data-ttu-id="aa5b2-201">Wenn eine Übereinstimmung vorhanden ist, wird die Methode verwendet die deserialisierte Parameterdaten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-201">If there is a match, the client method will be executed using the deserialized parameter data.</span></span>

<span data-ttu-id="aa5b2-202">Der Methodenaufruf kann überwacht werden, mithilfe von Tools wie [Fiddler.](http://fiddler2.com/)</span><span class="sxs-lookup"><span data-stu-id="aa5b2-202">The method call can be monitored using tools like [Fiddler.](http://fiddler2.com/)</span></span> <span data-ttu-id="aa5b2-203">Die folgende Abbildung zeigt einen Methodenaufruf von einem SignalR-Server an einem Webbrowserclient im Bereich "Protokolle" des Fiddler gesendet.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-203">The following image shows a method call sent from a SignalR server to a web browser client in the Logs pane of Fiddler.</span></span> <span data-ttu-id="aa5b2-204">Aufruf der Methode mit einem Hub aufgerufen gesendet wird `MoveShapeHub`, und die aufgerufene Methode wird aufgerufen, `updateShape`.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-204">The method call is being sent from a hub called `MoveShapeHub`, and the method being invoked is called `updateShape`.</span></span>

![Überblick über Fiddler-Protokoll, die mit SignalR-Datenverkehr](introduction-to-signalr/_static/image6.png)

<span data-ttu-id="aa5b2-206">In diesem Beispiel wird der Hub-Name identifiziert, mit der `H` Parameter; die Methode mit Namen identifiziert die `M` Parameter und die Daten gesendet werden, an die Methode wird mit identifiziert die `A` Parameter.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-206">In this example, the hub name is identified with the `H` parameter; the method name is identified with the `M` parameter, and the data being sent to the method is identified with the `A` parameter.</span></span> <span data-ttu-id="aa5b2-207">Die Anwendung, die diese Nachricht generiert wird erstellt, der [hochfrequente Echtzeit](tutorial-high-frequency-realtime-with-signalr.md) Lernprogramm.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-207">The application that generated this message is created in the [High-Frequency Realtime](tutorial-high-frequency-realtime-with-signalr.md) tutorial.</span></span>

### <a name="choosing-a-communication-model"></a><span data-ttu-id="aa5b2-208">Auswählen eines Modells für die Kommunikation</span><span class="sxs-lookup"><span data-stu-id="aa5b2-208">Choosing a communication model</span></span>

<span data-ttu-id="aa5b2-209">Die meisten Anwendungen sollten die Hubs-API verwenden.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-209">Most applications should use the Hubs API.</span></span> <span data-ttu-id="aa5b2-210">Die API Verbindungen konnte in den folgenden Situationen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="aa5b2-210">The Connections API could be used in the following circumstances:</span></span>

- <span data-ttu-id="aa5b2-211">Das Format der tatsächlichen Nachricht muss angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-211">The format of the actual message sent needs to be specified.</span></span>
- <span data-ttu-id="aa5b2-212">Der Entwickler bevorzugt mit einem Messaging- und verteilen-Modell statt mit einem Remoteaufruf-Modell arbeiten.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-212">The developer prefers to work with a messaging and dispatching model rather than a remote invocation model.</span></span>
- <span data-ttu-id="aa5b2-213">Eine vorhandene Anwendung, die eine e-Mail-Modell verwendet wird SignalR verwenden portiert werden.</span><span class="sxs-lookup"><span data-stu-id="aa5b2-213">An existing application that uses a messaging model is being ported to use SignalR.</span></span>