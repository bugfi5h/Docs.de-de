---
title: Erste Schritte mit Data Protection-APIs
author: rick-anderson
description: 
keywords: ASP.NET Core
ms.author: riande
manager: wpickett
ms.date: 10/14/2016
ms.topic: article
ms.assetid: 39b7a73c-29d4-4137-b311-49529adcf3cb
ms.technology: aspnet
ms.prod: asp.net-core
uid: security/data-protection/using-data-protection
ms.openlocfilehash: 2a381acf5faa7071fe4a22641037fcee11f6d362
ms.sourcegitcommit: 0b6c8e6d81d2b3c161cd375036eecbace46a9707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2017
---
# <a name="getting-started-with-the-data-protection-apis"></a><span data-ttu-id="56f4d-103">Erste Schritte mit Data Protection-APIs</span><span class="sxs-lookup"><span data-stu-id="56f4d-103">Getting Started with the Data Protection APIs</span></span>

<a name=security-data-protection-getting-started></a>

<span data-ttu-id="56f4d-104">Der einfachste Schutz Daten besteht aus der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="56f4d-104">At its simplest protecting data consists of the following steps:</span></span>

1. <span data-ttu-id="56f4d-105">Erstellen Sie eine Schutzvorrichtung aus einen Datenschutzanbieter.</span><span class="sxs-lookup"><span data-stu-id="56f4d-105">Create a data protector from a data protection provider.</span></span>

2. <span data-ttu-id="56f4d-106">Rufen Sie die Protect-Methode mit den Daten, die Sie schützen möchten.</span><span class="sxs-lookup"><span data-stu-id="56f4d-106">Call the Protect method with the data you want to protect.</span></span>

3. <span data-ttu-id="56f4d-107">Rufen Sie die Unprotect-Methode mit den Daten, die Sie in nur-Text wieder aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="56f4d-107">Call the Unprotect method with the data you want to turn back into plain text.</span></span>

<span data-ttu-id="56f4d-108">Die meisten Frameworks wie ASP.NET oder SignalR bereits das Data Protection-System konfigurieren und einen Dienstcontainer, die den Zugriff über Abhängigkeitsinjektion hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="56f4d-108">Most frameworks such as ASP.NET or SignalR already configure the data protection system and add it to a service container you access via dependency injection.</span></span> <span data-ttu-id="56f4d-109">Das folgende Beispiel zeigt einen Dienstcontainer für zielabhängigkeit konfigurieren und registrieren den Data Protection-Stapel, der Datenschutzanbieter über DI empfangen, erstellen eine Schutzvorrichtung und schützen und Aufheben des Schutzes von Daten</span><span class="sxs-lookup"><span data-stu-id="56f4d-109">The following sample demonstrates configuring a service container for dependency injection and registering the data protection stack, receiving the data protection provider via DI, creating a protector and protecting then unprotecting data</span></span>

<span data-ttu-id="56f4d-110">[!code-csharp[Main](../../security/data-protection/using-data-protection/samples/protectunprotect.cs?highlight=26,34,35,36,37,38,39,40)]</span><span class="sxs-lookup"><span data-stu-id="56f4d-110">[!code-csharp[Main](../../security/data-protection/using-data-protection/samples/protectunprotect.cs?highlight=26,34,35,36,37,38,39,40)]</span></span>

<span data-ttu-id="56f4d-111">Wenn Sie eine Schutzvorrichtung erstellen müssen Sie angeben, eine oder mehrere [Zweck Zeichenfolgen](consumer-apis/purpose-strings.md).</span><span class="sxs-lookup"><span data-stu-id="56f4d-111">When you create a protector you must provide one or more [Purpose Strings](consumer-apis/purpose-strings.md).</span></span> <span data-ttu-id="56f4d-112">Eine Zeichenfolge Zweck wird eine Isolation zwischen den Consumern, z. B. eine Schutzvorrichtung erstellt mit einer Zeichenfolge Zweck "Grün" würde nicht zum Aufheben des Schutzes von Daten, die durch eine Schutzvorrichtung bereitgestellt, mit dem Zweck "Violett".</span><span class="sxs-lookup"><span data-stu-id="56f4d-112">A purpose string provides isolation between consumers, for example a protector created with a purpose string of "green" would not be able to unprotect data provided by a protector with a purpose of "purple".</span></span>

>[!TIP]
> <span data-ttu-id="56f4d-113">Instanzen von IDataProtectionProvider und IDataProtector sind threadsicher für mehrere Aufrufer.</span><span class="sxs-lookup"><span data-stu-id="56f4d-113">Instances of IDataProtectionProvider and IDataProtector are thread-safe for multiple callers.</span></span> <span data-ttu-id="56f4d-114">Es richtet sich an, dass nach eine Komponente einen Verweis auf einen IDataProtector über einen Aufruf an CreateProtector abruft, diesen Verweis für mehrere Aufrufe von Schutz- und Unprotect verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="56f4d-114">It is intended that once a component gets a reference to an IDataProtector via a call to CreateProtector, it will use that reference for multiple calls to Protect and Unprotect.</span></span>
>
><span data-ttu-id="56f4d-115">Ein Aufruf von Unprotect löst CryptographicException aus, wenn die geschützte Nutzlast überprüft oder entschlüsselt werden kann.</span><span class="sxs-lookup"><span data-stu-id="56f4d-115">A call to Unprotect will throw CryptographicException if the protected payload cannot be verified or deciphered.</span></span> <span data-ttu-id="56f4d-116">Einige Komponenten Fehler ignorieren möchten Aufheben des Schutzes von während der Vorgänge eine Komponente, die Authentifizierungscookies liest möglicherweise diesen Fehler zu behandeln und die Anforderung zu behandeln, als ob es überhaupt kein Cookie hatte anstelle der sofortiges Anforderung schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="56f4d-116">Some components may wish to ignore errors during unprotect operations; a component which reads authentication cookies might handle this error and treat the request as if it had no cookie at all rather than fail the request outright.</span></span> <span data-ttu-id="56f4d-117">Komponenten, die über dieses Verhalten soll sollten CryptographicException speziell statt Angriffspunkt alle Ausnahmen abfangen.</span><span class="sxs-lookup"><span data-stu-id="56f4d-117">Components which want this behavior should specifically catch CryptographicException instead of swallowing all exceptions.</span></span>