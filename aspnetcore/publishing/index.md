---
title: "Übersicht über Hosting und Bereitstellung – ASP.NET Core"
author: tdykstra
description: "Übersicht über das Einrichten von Hostingumgebungen und das Bereitstellen von ASP.NET-Apps für diese."
keywords: ASP.NET Core
ms.author: riande
manager: wpickett
ms.date: 08/07/2017
ms.topic: article
ms.assetid: f0930c68-4d17-4748-adbf-801e17601eb6
ms.technology: aspnet
ms.prod: asp.net-core
uid: publishing/index
ms.openlocfilehash: 0de459128426c4d027606951592b1fe3fdd24fd9
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2017
---
# <a name="hosting-and-deployment-overview-for-aspnet-core-apps"></a>Übersicht über Hosting und Bereitstellung für ASP.NET Core-Apps

Hier sind die wichtigsten Schritte, die Sie für das Bereitstellen einer ASP.NET Core-App in eine Hostumgebung durchführen müssen:

* Veröffentlichen Sie die App in einem Ordner auf dem Hostserver.
* Richten Sie einen Prozessmanager ein, der die App startet, wenn Anforderungen eingehen und sie nach einem Absturz oder Serverneustart neu startet.
* Richten Sie einen Reverseproxy ein, der die Anforderung an die App weiterleitet.

## <a name="publish-to-a-folder"></a>Veröffentlichen in einem Ordner 

Der CLI-Befehl [dotnet publish](https://docs.microsoft.com/dotnet/articles/core/tools/dotnet-publish) kompiliert Anwendungscode und kopiert die Dateien, die zum Ausführen der Anwendung benötigt werden, in den Ordner *publish*. Bei der Bereitstellung von Visual Studio wird der `dotnet publish`-Schritt automatisch für Sie ausgeführt, bevor die Dateien in das Bereitstellungsziel kopiert werden.

### <a name="folder-contents"></a>Ordnerinhalte

Der Ordner *publish* enthält *EXE*- und *DLL*-Dateien für die Anwendung, ihre Abhängigkeiten und optional die .NET-Runtime.

Eine .NET Core-App kann *eigenständig* oder *Framework-abhängig* veröffentlicht werden. Wenn die App eigenständig ist, sind die *DLL*-Dateien, die die .NET-Runtime enthalten, im Ordner *publish* enthalten.  Wenn die App Framework-abhängig ist, sind die Dateien für die .NET-Runtime nicht enthalten, da die App über einen Verweis auf eine auf dem Computer installierte Version von .NET verfügt. Das Standardmodell für die Bereitstellung ist Framework-abhängig. Weitere Informationen finden Sie unter [.NET Core application deployment (.NET Core-Anwendungsbereitstellung)](https://docs.microsoft.com/dotnet/articles/core/deploying/index).

Zusätzlich zu den *EXE*- und *DLL*-Dateien enthält der Ordner *publish* für eine ASP.NET Core-App üblicherweise noch Konfigurationsdateien, statische Objekte und MVC-Ansichten.  Weitere Informationen finden Sie unter [Directory structure (Verzeichnisstruktur)](xref:hosting/directory-structure).

## <a name="set-up-a-process-manager"></a>Einrichten eines Prozessmanagers

Bei einer ASP.NET Core-App handelt es sich um eine Konsolen-App, die gestartet werden muss, wenn ein Server startet und nach Abstürzen neu startet. Sie benötigen einen Prozessmanager, um die Starts und Neustarts zu automatisieren. Die am häufigsten verwendeten Prozessmanager für ASP.NET Core sind [Nginx](xref:publishing/linuxproduction) und [Apache](xref:publishing/apache-proxy) unter Linux und [IIS](xref:publishing/iis) und [Windows Service](xref:hosting/windows-service) unter Windows.

## <a name="set-up-a-reverse-proxy"></a>Einrichten eines Reverseproxys

# <a name="aspnet-core-2xtabaspnetcore2x"></a>[ASP.NET Core 2.x](#tab/aspnetcore2x)

Wenn Ihre App den [Kestrel](xref:fundamentals/servers/kestrel)-Webserver verwendet, können Sie [Nginx](xref:publishing/linuxproduction), [Apache](xref:publishing/apache-proxy) oder [IIS](xref:publishing/iis) als Reverseproxy verwenden. Ein Reverseproxyserver empfängt HTTP-Anforderungen aus dem Internet und leitet diese nach einer vorbereitenden Verarbeitung an Kestrel weiter. Weitere Informationen finden Sie unter [When to use Kestrel with a reverse proxy (Verwenden von Kestrel mit einem Reverseproxy)](xref:fundamentals/servers/kestrel?tabs=aspnetcore2x#when-to-use-kestrel-with-a-reverse-proxy).

# <a name="aspnet-core-1xtabaspnetcore1x"></a>[ASP.NET Core 1.x](#tab/aspnetcore1x)

Wenn Ihre App den [Kestrel](xref:fundamentals/servers/kestrel)-Webserver verwendet und ins Internet gestellt wird, müssen Sie [Nginx](xref:publishing/linuxproduction), [Apache](xref:publishing/apache-proxy) oder [IIS](xref:publishing/iis) als Reverseproxyserver verwenden. Ein Reverseproxyserver empfängt HTTP-Anforderungen aus dem Internet und leitet diese nach einer vorbereitenden Verarbeitung an Kestrel weiter. Der Hauptgrund für die Verwendung eines Reverseproxys ist Sicherheit. Weitere Informationen finden Sie unter [When to use Kestrel with a reverse proxy (Verwenden von Kestrel mit einem Reverseproxy)](xref:fundamentals/servers/kestrel?tabs=aspnetcore1x#when-to-use-kestrel-with-a-reverse-proxy).

---

## <a name="using-visual-studio-and-msbuild-to-automate-deployment"></a>Verwenden von Visual Studio und MSBuild zum Automatisieren der Bereitstellung

Die Bereitstellung erfordert neben dem Kopieren der Ausgabe von `dotnet publish` auf einen Server oft zusätzliche Aufgaben. Beispielsweise sollten Sie zusätzliche Dateien in den Ordner *publish* kopieren oder Dateien daraus ausschließen. Visual Studio verwendet MSBuild für die Webbereitstellung, und Sie können MSBuild anpassen, um viele weitere Aufgaben während der Bereitstellung durchzuführen. Weitere Informationen finden Sie unter [Publish profiles in Visual Studio (Veröffentlichen von Profilen in Visual Studio)](xref:publishing/web-publishing-vs) und im Buch [Using MSBuild and Team Foundation Build (Verwenden von MSBuild und Team Foundation Build)](http://msbuildbook.com/).

Sie können direkte Bereitstellungen von Visual Studio in Azure App Service vornehmen, indem Sie [das Webfeature „Veröffentlichen“](xref:tutorials/publish-to-azure-webapp-using-vs) oder die [integrierte Git-Unterstützung](xref:publishing/azure-continuous-deployment) verwenden. Visual Studio Team Services unterstützt die [continuous deployment to Azure App Service (fortlaufende Bereitstellung in Azure App Service)](https://www.visualstudio.com/docs/build/aspnet/core/quick-to-azure).

## <a name="publishing-to-azure"></a>Veröffentlichen in Azure

Anweisungen zum Veröffentlichen dieser App in Azure mit Visual Studio finden Sie unter [Veröffentlichen einer ASP.NET Core-Web-App in Azure App Service mit Visual Studio](xref:tutorials/publish-to-azure-webapp-using-vs).  Die App kann auch über die [Befehlszeile](xref:tutorials/publish-to-azure-webapp-using-cli) in Azure veröffentlicht werden.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

Weitere Informationen zum Verwenden von Docker als Hostumgebung finden Sie unter [Host ASP.NET Core apps in Docker (Hosten von ASP.NET Core-Apps in Docker)](xref:publishing/docker).
