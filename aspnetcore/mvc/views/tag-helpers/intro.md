---
title: Tag-Hilfsprogramme in ASP.NET Core
author: rick-anderson
description: Erfahren Sie, was Tag Hilfsprogramme sind und wie Ihre Verwendung in ASP.NET Core.
keywords: ASP.NET Core, Tag-Hilfsprogramme
ms.author: riande
manager: wpickett
ms.date: 7/14/2017
ms.topic: article
ms.technology: aspnet
ms.prod: asp.net-core
uid: mvc/views/tag-helpers/intro
ms.custom: H1Hack27Feb2017
ms.openlocfilehash: 8b1de37d93f5dca2d6b6be24c429b5971692e17e
ms.sourcegitcommit: 0b6c8e6d81d2b3c161cd375036eecbace46a9707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2017
---
# <a name="introduction-to-tag-helpers-in-aspnet-core"></a><span data-ttu-id="1f971-104">Einführung in die Tag-Hilfsprogramme in ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1f971-104">Introduction to Tag Helpers in ASP.NET Core</span></span> 

<span data-ttu-id="1f971-105">Durch [Rick Anderson](https://twitter.com/RickAndMSFT)</span><span class="sxs-lookup"><span data-stu-id="1f971-105">By [Rick Anderson](https://twitter.com/RickAndMSFT)</span></span>

## <a name="what-are-tag-helpers"></a><span data-ttu-id="1f971-106">Was sind Hilfen Tag?</span><span class="sxs-lookup"><span data-stu-id="1f971-106">What are Tag Helpers?</span></span>

<span data-ttu-id="1f971-107">Tag-Hilfsprogrammen aktivieren serverseitiger Code zu erstellen und das rendering von HTML-Elementen in Razor-Dateien teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="1f971-107">Tag Helpers enable server-side code to participate in creating and rendering HTML elements in Razor files.</span></span> <span data-ttu-id="1f971-108">Z. B. die integrierten `ImageTagHelper` eine Versionsnummer an den Namen des Abbilds angefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="1f971-108">For example, the built-in `ImageTagHelper` can append a version number to the image name.</span></span> <span data-ttu-id="1f971-109">Bei jeder Änderung der Image generiert der Server eine neue eindeutige Version für das Bild aus, damit Clients sichergestellt, dass werden das aktuelle Bild (statt eine veraltete zwischengespeicherte Image).</span><span class="sxs-lookup"><span data-stu-id="1f971-109">Whenever the image changes, the server generates a new unique version for the image, so clients are guaranteed to get the current image (instead of a stale cached image).</span></span> <span data-ttu-id="1f971-110">Es gibt viele integrierte Tag Hilfen für allgemeine Aufgaben – z. B. das Erstellen von Formularen, Links, Laden von Ressourcen und weitere- und sogar noch stärker verfügbar in öffentlichen GitHub-Repositorys und als NuGet-Pakete.</span><span class="sxs-lookup"><span data-stu-id="1f971-110">There are many built-in Tag Helpers for common tasks - such as creating forms, links, loading assets and more - and even more available in public GitHub repositories and as NuGet packages.</span></span> <span data-ttu-id="1f971-111">Tag-Hilfsprogramme in c# erstellt wurden, und sie Zielen auf HTML-Elemente, die basierend auf Elementnamen, Attributnamen oder übergeordneten Tags.</span><span class="sxs-lookup"><span data-stu-id="1f971-111">Tag Helpers are authored in C#, and they target HTML elements based on element name, attribute name, or parent tag.</span></span> <span data-ttu-id="1f971-112">Z. B. die integrierten `LabelTagHelper` paketaktualisierungen HTML `<label>` Element bei der `LabelTagHelper` Attribute angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1f971-112">For example, the built-in `LabelTagHelper` can target the HTML `<label>` element when the `LabelTagHelper` attributes are applied.</span></span> <span data-ttu-id="1f971-113">Wenn Sie sich mit vertraut [HTML-Hilfsmethoden](http://stephenwalther.com/archive/2009/03/03/chapter-6-understanding-html-helpers), Tag Hilfen zu reduzieren, die explizite Übergänge zwischen HTML und c# in Razor-Ansichten.</span><span class="sxs-lookup"><span data-stu-id="1f971-113">If you're familiar with [HTML Helpers](http://stephenwalther.com/archive/2009/03/03/chapter-6-understanding-html-helpers), Tag Helpers reduce the explicit transitions between HTML and C# in Razor views.</span></span> <span data-ttu-id="1f971-114">In vielen Fällen HTML-Hilfsmethoden bieten eine alternative Methode in einer bestimmten Tag-Hilfsprogramm, aber es ist wichtig zu wissen, dass die Tag-Hilfsprogrammen HTML-Hilfsmethoden nicht ersetzen, und es ist keines Tag-Hilfsprogramms für jedes HTML-Hilfsobjekt.</span><span class="sxs-lookup"><span data-stu-id="1f971-114">In many cases, HTML Helpers provide an alternative approach to a specific Tag Helper, but it's important to recognize that Tag Helpers do not replace HTML Helpers and there is not a Tag Helper for each HTML Helper.</span></span> <span data-ttu-id="1f971-115">[Tag-Hilfsprogramme, die im Vergleich zu HTML-Hilfsmethoden](#tag-helpers-compared-to-html-helpers) werden die Unterschiede im Detail erläutert.</span><span class="sxs-lookup"><span data-stu-id="1f971-115">[Tag Helpers compared to HTML Helpers](#tag-helpers-compared-to-html-helpers) explains the differences in more detail.</span></span>

## <a name="what-tag-helpers-provide"></a><span data-ttu-id="1f971-116">Was Tag Hilfsvorlagen können</span><span class="sxs-lookup"><span data-stu-id="1f971-116">What Tag Helpers provide</span></span>

<span data-ttu-id="1f971-117">**Eine HTML-freundliche entwicklungserfahrung** zum größten Teil, sieht die Razor-Markup mithilfe von Hilfsprogrammen Tag standard-HTML.</span><span class="sxs-lookup"><span data-stu-id="1f971-117">**An HTML-friendly development experience** For the most part, Razor markup using Tag Helpers looks like standard HTML.</span></span> <span data-ttu-id="1f971-118">Sich mit HTML/CSS/JavaScript-Front-End-Designer können Razor bearbeiten, ohne das Erlernen von C#-Razor-Syntax.</span><span class="sxs-lookup"><span data-stu-id="1f971-118">Front-end designers conversant with HTML/CSS/JavaScript can edit Razor without learning C# Razor syntax.</span></span>

<span data-ttu-id="1f971-119">**Eine umfassende IntelliSense-Umgebung zum Erstellen von HTML und Razor-Markup** Dies ist im Spitze Gegensatz zu anderen HTML-Hilfen, mit der vorherigen Vorgehensweise bei der serverseitigen Erstellung des Markups in Razor-Ansichten.</span><span class="sxs-lookup"><span data-stu-id="1f971-119">**A rich IntelliSense environment for creating HTML and Razor markup** This is in sharp contrast to HTML Helpers, the previous approach to server-side creation of markup in Razor views.</span></span> <span data-ttu-id="1f971-120">[Tag-Hilfsprogramme, die im Vergleich zu HTML-Hilfsmethoden](#tag-helpers-compared-to-html-helpers) werden die Unterschiede im Detail erläutert.</span><span class="sxs-lookup"><span data-stu-id="1f971-120">[Tag Helpers compared to HTML Helpers](#tag-helpers-compared-to-html-helpers) explains the differences in more detail.</span></span> <span data-ttu-id="1f971-121">[IntelliSense-Unterstützung für Tag Hilfsprogramme](#intellisense-support-for-tag-helpers) die IntelliSense-Umgebung erläutert.</span><span class="sxs-lookup"><span data-stu-id="1f971-121">[IntelliSense support for Tag Helpers](#intellisense-support-for-tag-helpers) explains the IntelliSense environment.</span></span> <span data-ttu-id="1f971-122">Auch Entwickler, die mit Razor-C#-Syntax aufgetreten sind produktiver verwenden die Tag-Hilfsprogrammen als das Schreiben von C#-Razor-Markup.</span><span class="sxs-lookup"><span data-stu-id="1f971-122">Even developers experienced with Razor C# syntax are more productive using Tag Helpers than writing C# Razor markup.</span></span>

<span data-ttu-id="1f971-123">**Eine Möglichkeit, Sie produktiver und produzieren robuster und zuverlässiger und wartbarem Code mit Informationen, die nur verfügbar, auf dem Server** z. B. in der Vergangenheit das Mantra auf das Aktualisieren von Abbildern bei einer Änderung der Name des Bilds geändert wurde das Bild.</span><span class="sxs-lookup"><span data-stu-id="1f971-123">**A way to make you more productive and able to produce more robust, reliable, and maintainable code using information only available on the server** For example, historically the mantra on updating images was to change the name of the image when you change the image.</span></span> <span data-ttu-id="1f971-124">Bilder aggressiv zur Verbesserung der Leistung zwischengespeichert werden soll, und, wenn Sie den Namen eines Bilds ändern, riskieren Sie Clients, die eine veraltete Kopie abrufen.</span><span class="sxs-lookup"><span data-stu-id="1f971-124">Images should be aggressively cached for performance reasons, and unless you change the name of an image, you risk clients getting a stale copy.</span></span> <span data-ttu-id="1f971-125">In der Vergangenheit nachdem ein Bild bearbeitet wurde, der Name geändert werden mussten, und jeder Verweis auf das Bild in der Web-app erforderlich sind, aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f971-125">Historically, after an image was edited, the name had to be changed and each reference to the image in the web app needed to be updated.</span></span> <span data-ttu-id="1f971-126">Dies ist nicht nur sehr arbeitsintensiv rechenintensiven, sie entspricht fehleranfällig (Sie kann verpasst haben einen Verweis, geben Sie versehentlich das falsche Zeichenfolge usw.) Die integrierte `ImageTagHelper` können erledigen dies automatisch.</span><span class="sxs-lookup"><span data-stu-id="1f971-126">Not only is this very labor intensive, it's also error prone (you could miss a reference, accidentally enter the wrong string, etc.) The built-in `ImageTagHelper` can do this for you automatically.</span></span> <span data-ttu-id="1f971-127">Die `ImageTagHelper` kann eine Version angefügt-Zahl in den Namen des Abbilds, damit die Änderung das Bild vom Server automatisch eine neue eindeutige Version für das Image generiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f971-127">The `ImageTagHelper` can append a version number to the image name, so whenever the image changes, the server automatically generates a new unique version for the image.</span></span> <span data-ttu-id="1f971-128">Clients werden sichergestellt, dass das aktuelle Bild.</span><span class="sxs-lookup"><span data-stu-id="1f971-128">Clients are guaranteed to get the current image.</span></span> <span data-ttu-id="1f971-129">Diese einsparungen Stabilität und Arbeit im Grunde frei stammen, mithilfe der `ImageTagHelper`.</span><span class="sxs-lookup"><span data-stu-id="1f971-129">This robustness and labor savings comes essentially free by using the `ImageTagHelper`.</span></span>

<span data-ttu-id="1f971-130">Die meisten integrierten Tag Hilfsprogramme vorhandenen HTML-Elemente als Ziel und geben Sie serverseitige Attribute für das Element.</span><span class="sxs-lookup"><span data-stu-id="1f971-130">Most of the built-in Tag Helpers target existing HTML elements and provide server-side attributes for the element.</span></span> <span data-ttu-id="1f971-131">Z. B. die `<input>` Element verwendet, die in vielen der Sichten in der *Ansichten oder des Kontos* Ordner enthält die `asp-for` -Attribut, das den Namen der Eigenschaft angegebene Modell in die gerenderte HTML extrahiert.</span><span class="sxs-lookup"><span data-stu-id="1f971-131">For example, the `<input>` element used in many of the views in the *Views/Account* folder contains the `asp-for` attribute, which extracts the name of the specified model property into the rendered HTML.</span></span> <span data-ttu-id="1f971-132">Das folgende Razor-Markup:</span><span class="sxs-lookup"><span data-stu-id="1f971-132">The following Razor markup:</span></span>

```html
<label asp-for="Email"></label>
```

<span data-ttu-id="1f971-133">Generiert den folgenden HTML-Code:</span><span class="sxs-lookup"><span data-stu-id="1f971-133">Generates the following HTML:</span></span>

```html
<label for="Email">Email</label>
```

<span data-ttu-id="1f971-134">Die `asp-for` Attribut von zur Verfügung gestellt wird die `For` Eigenschaft in der `LabelTagHelper`.</span><span class="sxs-lookup"><span data-stu-id="1f971-134">The `asp-for` attribute is made available by the `For` property in the `LabelTagHelper`.</span></span> <span data-ttu-id="1f971-135">Finden Sie unter [Authoring Tag Hilfsprogramme](authoring.md) für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="1f971-135">See [Authoring Tag Helpers](authoring.md) for more information.</span></span>

## <a name="managing-tag-helper-scope"></a><span data-ttu-id="1f971-136">Verwalten von Bereich Hilfsprogramm-Tag</span><span class="sxs-lookup"><span data-stu-id="1f971-136">Managing Tag Helper scope</span></span>

<span data-ttu-id="1f971-137">Tag-Hilfsprogrammen Bereich wird gesteuert, indem eine Kombination von `@addTagHelper`, `@removeTagHelper`, und die "!" opt-Out-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="1f971-137">Tag Helpers scope is controlled by a combination of `@addTagHelper`, `@removeTagHelper`, and the "!" opt-out character.</span></span>

<a name=add-helper-label></a>

### <a name="addtaghelper-makes-tag-helpers-available"></a><span data-ttu-id="1f971-138">`@addTagHelper`Stellt die Tag-Hilfsprogrammen zur Verfügung</span><span class="sxs-lookup"><span data-stu-id="1f971-138">`@addTagHelper` makes Tag Helpers available</span></span>

<span data-ttu-id="1f971-139">Bei der Erstellung einer neuen ASP.NET Core-Web-app mit dem Namen *AuthoringTagHelpers* (mit keine Authentifizierung), die folgenden *Views/_ViewImports.cshtml* Datei wird dem Projekt hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="1f971-139">If you create a new ASP.NET Core web app named *AuthoringTagHelpers* (with no authentication), the following *Views/_ViewImports.cshtml* file will be added to your project:</span></span>

<span data-ttu-id="1f971-140">[!code-html[Main](../../../mvc/views/tag-helpers/authoring/sample/AuthoringTagHelpers/src/AuthoringTagHelpers/Views/_ViewImportsCopy.cshtml?highlight=2&range=2-3)]</span><span class="sxs-lookup"><span data-stu-id="1f971-140">[!code-html[Main](../../../mvc/views/tag-helpers/authoring/sample/AuthoringTagHelpers/src/AuthoringTagHelpers/Views/_ViewImportsCopy.cshtml?highlight=2&range=2-3)]</span></span>

<span data-ttu-id="1f971-141">Die `@addTagHelper` -Direktive macht Tag Hilfen zur Ansicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1f971-141">The `@addTagHelper` directive makes Tag Helpers available to the view.</span></span> <span data-ttu-id="1f971-142">In diesem Fall die Ansichtsdatei ist *Views/_ViewImports.cshtml*, die standardmäßig von allen Dateien werden in geerbt wird die *Ansichten* Ordner und seinen Unterverzeichnissen; Tag Hilfen zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="1f971-142">In this case, the view file is *Views/_ViewImports.cshtml*, which by default is inherited by all view files in the *Views* folder and sub-directories; making Tag Helpers available.</span></span> <span data-ttu-id="1f971-143">Der obige Code verwendet die Platzhaltersyntax ("\*") angeben, dass alle Tag-Hilfsprogramme in der angegebenen Assembly (*Microsoft.AspNetCore.Mvc.TagHelpers*) stehen dann jeder einzelnen Datei anzeigen, in der *Ansichten* Verzeichnis oder Unterverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="1f971-143">The code above uses the wildcard syntax ("\*") to specify that all Tag Helpers in the specified assembly (*Microsoft.AspNetCore.Mvc.TagHelpers*) will be available to every view file in the *Views* directory or sub-directory.</span></span> <span data-ttu-id="1f971-144">Der erste Parameter nach `@addTagHelper` gibt die Tag-Hilfsprogramme zum Laden (Code verwenden wir "\*" für alle Tags Hilfsprogramme), und der zweite Parameter "Microsoft.AspNetCore.Mvc.TagHelpers" gibt die Assembly mit der Tag-Hilfsprogramme.</span><span class="sxs-lookup"><span data-stu-id="1f971-144">The first parameter after `@addTagHelper` specifies the Tag Helpers to load (we are using "\*" for all Tag Helpers), and the second parameter "Microsoft.AspNetCore.Mvc.TagHelpers" specifies the assembly containing the Tag Helpers.</span></span> <span data-ttu-id="1f971-145">*Microsoft.AspNetCore.Mvc.TagHelpers* ist die Assembly für die integrierte Basishilfsprogramme Tag ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="1f971-145">*Microsoft.AspNetCore.Mvc.TagHelpers* is the assembly for the built-in ASP.NET Core Tag Helpers.</span></span>

<span data-ttu-id="1f971-146">Um alle Hilfsprogramme Tag in diesem Projekt verfügbar zu machen (wodurch erstellt eine Assembly mit dem Namen *AuthoringTagHelpers*), nutzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1f971-146">To expose all of the Tag Helpers in this project (which creates an assembly named *AuthoringTagHelpers*), you would use the following:</span></span>

<span data-ttu-id="1f971-147">[!code-html[Main](../../../mvc/views/tag-helpers/authoring/sample/AuthoringTagHelpers/src/AuthoringTagHelpers/Views/_ViewImportsCopy.cshtml?highlight=3)]</span><span class="sxs-lookup"><span data-stu-id="1f971-147">[!code-html[Main](../../../mvc/views/tag-helpers/authoring/sample/AuthoringTagHelpers/src/AuthoringTagHelpers/Views/_ViewImportsCopy.cshtml?highlight=3)]</span></span>

<span data-ttu-id="1f971-148">Wenn Ihr Projekt enthält eine `EmailTagHelper` mit Standard-Namespace (`AuthoringTagHelpers.TagHelpers.EmailTagHelper`), können Sie den vollqualifizierten Namen (FQN) der Hilfsprogramm-Tag angeben:</span><span class="sxs-lookup"><span data-stu-id="1f971-148">If your project contains an `EmailTagHelper` with the default namespace (`AuthoringTagHelpers.TagHelpers.EmailTagHelper`), you can provide the fully qualified name (FQN) of the Tag Helper:</span></span>

<!-- literal_block {"ids": [], "linenos": false, "xml:space": "preserve", "language": "html", "highlight_args": {"hl_lines": [3]}} -->

```html
@using AuthoringTagHelpers
@addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers
@addTagHelper AuthoringTagHelpers.TagHelpers.EmailTagHelper, AuthoringTagHelpers
```

<span data-ttu-id="1f971-149">Zum Hinzufügen eines Tag-Hilfsprogramms zu einer Ansicht mithilfe einer FQN Sie zunächst die FQN hinzufügen (`AuthoringTagHelpers.TagHelpers.EmailTagHelper`), und klicken Sie dann den Assemblynamen (*AuthoringTagHelpers*).</span><span class="sxs-lookup"><span data-stu-id="1f971-149">To add a Tag Helper to a view using an FQN, you first add the FQN (`AuthoringTagHelpers.TagHelpers.EmailTagHelper`), and then the assembly name (*AuthoringTagHelpers*).</span></span> <span data-ttu-id="1f971-150">Die meisten Entwickler verwenden möchten, die "\*" Platzhaltersyntax.</span><span class="sxs-lookup"><span data-stu-id="1f971-150">Most developers prefer to use the  "\*" wildcard syntax.</span></span> <span data-ttu-id="1f971-151">Die Platzhaltersyntax können Sie das Platzhalterzeichen einfügen "\*" als Suffix in einer FQN.</span><span class="sxs-lookup"><span data-stu-id="1f971-151">The wildcard syntax allows you to insert the wildcard character "\*" as the suffix in an FQN.</span></span> <span data-ttu-id="1f971-152">Die folgenden Direktiven wird z. B. angezeigt, der `EmailTagHelper`:</span><span class="sxs-lookup"><span data-stu-id="1f971-152">For example, any of the following directives will bring in the `EmailTagHelper`:</span></span>

```csharp
@addTagHelper AuthoringTagHelpers.TagHelpers.E*, AuthoringTagHelpers
@addTagHelper AuthoringTagHelpers.TagHelpers.Email*, AuthoringTagHelpers
```

<span data-ttu-id="1f971-153">Wie bereits erwähnt, Hinzufügen der `@addTagHelper` -Direktive der *Views/_ViewImports.cshtml* Datei stellt das Tag-Hilfsobjekt, der zur Verfügung, alle Dateien in der *Ansichten* Verzeichnis und die Unterverzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="1f971-153">As mentioned previously, adding the `@addTagHelper` directive to the *Views/_ViewImports.cshtml* file makes the Tag Helper available to all view files in the *Views* directory and sub-directories.</span></span> <span data-ttu-id="1f971-154">Sie können die `@addTagHelper` -Direktive in Dateien bestimmte anzeigen, wenn Sie verfügbar zu machen das Tag-Hilfsobjekt, um nur diese Sichten teilnehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="1f971-154">You can use the `@addTagHelper` directive in specific view files if you want to opt-in to exposing the Tag Helper to only those views.</span></span>

<a name=remove-razor-directives-label></a>

### <a name="removetaghelper-removes-tag-helpers"></a><span data-ttu-id="1f971-155">`@removeTagHelper`Entfernt die Tag-Hilfsprogramme</span><span class="sxs-lookup"><span data-stu-id="1f971-155">`@removeTagHelper` removes Tag Helpers</span></span>

<span data-ttu-id="1f971-156">Die `@removeTagHelper` hat die gleichen zwei Parameter wie `@addTagHelper`, und es entfernt ein Tag-Hilfsprogramm, das Sie zuvor hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="1f971-156">The `@removeTagHelper` has the same two parameters as `@addTagHelper`, and it removes a Tag Helper that was previously added.</span></span> <span data-ttu-id="1f971-157">Beispielsweise `@removeTagHelper` auf eine bestimmte Ansicht entfernt das angegebene Tag Hilfsobjekt aus der Sicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="1f971-157">For example, `@removeTagHelper` applied to a specific view removes the specified Tag Helper from the view.</span></span> <span data-ttu-id="1f971-158">Mit `@removeTagHelper` in einem *Views/Folder/_ViewImports.cshtml* Datei entfernt das angegebene Tag Hilfsobjekt aus alle Ansichten in *Ordner*.</span><span class="sxs-lookup"><span data-stu-id="1f971-158">Using `@removeTagHelper` in a *Views/Folder/_ViewImports.cshtml* file removes the specified Tag Helper from all of the views in *Folder*.</span></span>

### <a name="controlling-tag-helper-scope-with-the-viewimportscshtml-file"></a><span data-ttu-id="1f971-159">Steuern des Hilfsprogramm-Tag-Bereich mit der *_ViewImports.cshtml* Datei</span><span class="sxs-lookup"><span data-stu-id="1f971-159">Controlling Tag Helper scope with the *_ViewImports.cshtml* file</span></span>

<span data-ttu-id="1f971-160">Können Sie hinzufügen, eine *_ViewImports.cshtml* Modul wendet die Anweisungen auf einen beliebigen Ordner anzeigen und die Ansicht aus beiden dieser Datei und die *Views/_ViewImports.cshtml* Datei.</span><span class="sxs-lookup"><span data-stu-id="1f971-160">You can add a *_ViewImports.cshtml* to any view folder, and the view engine applies the directives from both that file and the *Views/_ViewImports.cshtml* file.</span></span> <span data-ttu-id="1f971-161">Wenn Sie eine leere hinzugefügt *Views/Home/_ViewImports.cshtml* Datei für die *Home* Ansichten, gäbe es keine Änderung da die *_ViewImports.cshtml* Datei ist additiv.</span><span class="sxs-lookup"><span data-stu-id="1f971-161">If you added an empty *Views/Home/_ViewImports.cshtml* file for the *Home* views, there would be no change because the *_ViewImports.cshtml* file is additive.</span></span> <span data-ttu-id="1f971-162">Alle `@addTagHelper` Direktiven, die Sie hinzufügen, die *Views/Home/_ViewImports.cshtml* Datei (nicht in der Standardeinstellung sind *Views/_ViewImports.cshtml* Datei) würde verfügbar machen diese Hilfsprogramme Tag mit Ansichten nur in der *Home* Ordner.</span><span class="sxs-lookup"><span data-stu-id="1f971-162">Any `@addTagHelper` directives you add to the *Views/Home/_ViewImports.cshtml* file (that are not in the default *Views/_ViewImports.cshtml* file) would expose those Tag Helpers to views only in the *Home* folder.</span></span>

<a name="opt-out"></a>

### <a name="opting-out-of-individual-elements"></a><span data-ttu-id="1f971-163">Wenn Sie keine einzelne Elemente</span><span class="sxs-lookup"><span data-stu-id="1f971-163">Opting out of individual elements</span></span>

<span data-ttu-id="1f971-164">Sie können ein Tag Hilfsprogramm auf datenelementebene mit dem Tag Helper Ausschlussverfahren Zeichen deaktivieren ("!").</span><span class="sxs-lookup"><span data-stu-id="1f971-164">You can disable a Tag Helper at the element level with the Tag Helper opt-out character ("!").</span></span> <span data-ttu-id="1f971-165">Beispielsweise `Email` -Überprüfung deaktiviert ist, der `<span>` mit dem Tag Helper Ausschlussverfahren Zeichen:</span><span class="sxs-lookup"><span data-stu-id="1f971-165">For example, `Email` validation is disabled in the `<span>` with the Tag Helper opt-out character:</span></span>

```csharp
<!span asp-validation-for="Email" class="text-danger"></!span>
```

<span data-ttu-id="1f971-166">Sie müssen das Tag Helper Ausschlussverfahren Zeichen auf dem Start- und Endtag anwenden.</span><span class="sxs-lookup"><span data-stu-id="1f971-166">You must apply the Tag Helper opt-out character to the opening and closing tag.</span></span> <span data-ttu-id="1f971-167">(Visual Studio-Editor fügt automatisch die Opt-Out Zeichen an das Endtag, wenn Sie eine des öffnenden Tags hinzufügen).</span><span class="sxs-lookup"><span data-stu-id="1f971-167">(The Visual Studio editor automatically adds the opt-out character to the closing tag when you add one to the opening tag).</span></span> <span data-ttu-id="1f971-168">Nachdem Sie das Opt-Out Zeichen hinzugefügt haben, werden des Elements und die Attribute Tag Helper in eine besondere Schriftart nicht mehr angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f971-168">After you add the opt-out character, the element and Tag Helper attributes are no longer displayed in a distinctive font.</span></span>

<a name=prefix-razor-directives-label></a>

### <a name="using-taghelperprefix-to-make-tag-helper-usage-explicit"></a><span data-ttu-id="1f971-169">Mithilfe von `@tagHelperPrefix` zum Hilfsprogramm-Tag-Verwendung als explizite Anforderung festgelegt</span><span class="sxs-lookup"><span data-stu-id="1f971-169">Using `@tagHelperPrefix` to make Tag Helper usage explicit</span></span>

<span data-ttu-id="1f971-170">Die `@tagHelperPrefix` Richtlinie ermöglicht Ihnen die Angabe Präfixzeichenfolge "Tag" Tag-Helper-Unterstützung zu aktivieren und Tag Helper Verwendung als explizite Anforderung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1f971-170">The `@tagHelperPrefix` directive allows you to specify a tag prefix string to enable Tag Helper support and to make Tag Helper usage explicit.</span></span> <span data-ttu-id="1f971-171">Sie können z. B. das folgende Markup hinzu Hinzufügen der *Views/_ViewImports.cshtml* Datei:</span><span class="sxs-lookup"><span data-stu-id="1f971-171">For example, you could add the following markup to the *Views/_ViewImports.cshtml* file:</span></span>

```html
@tagHelperPrefix th:
```
<span data-ttu-id="1f971-172">Code die folgende Abbildung, wird das Präfix für Tag Helper so eingerichtet `th:`, sodass nur die Elemente, die mit dem Präfix `th:` Tag-Hilfsprogramme (Tag Helper-fähigen Elemente haben eine besondere Schriftart) unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1f971-172">In the code image below, the Tag Helper prefix is set to `th:`, so only those elements using the prefix `th:` support Tag Helpers (Tag Helper-enabled elements have a distinctive font).</span></span> <span data-ttu-id="1f971-173">Die `<label>` und `<input>` Elemente haben das Präfix für Tag Helper und Tag Helper beim aktiviert die `<span>` Element nicht.</span><span class="sxs-lookup"><span data-stu-id="1f971-173">The `<label>` and `<input>` elements have the Tag Helper prefix and are Tag Helper-enabled, while the `<span>` element does not.</span></span>

![Bild](intro/_static/thp.png)

<span data-ttu-id="1f971-175">Dieselbe gelten die Hierarchieregeln zum `@addTagHelper` gelten auch für `@tagHelperPrefix`.</span><span class="sxs-lookup"><span data-stu-id="1f971-175">The same hierarchy rules that apply to `@addTagHelper` also apply to `@tagHelperPrefix`.</span></span>

## <a name="intellisense-support-for-tag-helpers"></a><span data-ttu-id="1f971-176">IntelliSense-Unterstützung für den Tag-Hilfsprogramme</span><span class="sxs-lookup"><span data-stu-id="1f971-176">IntelliSense support for Tag Helpers</span></span>

<span data-ttu-id="1f971-177">Beim Erstellen einer neuen ASP.NET Web-app in Visual Studio fügt er das NuGet-Paket "Microsoft.AspNetCore.Razor.Tools" hinzu.</span><span class="sxs-lookup"><span data-stu-id="1f971-177">When you create a new ASP.NET web app in Visual Studio, it adds the NuGet package "Microsoft.AspNetCore.Razor.Tools".</span></span> <span data-ttu-id="1f971-178">Dies ist das Paket, das Tag Helper Tools hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="1f971-178">This is the package that adds Tag Helper tooling.</span></span>

<span data-ttu-id="1f971-179">Berücksichtigen Sie beim Schreiben einer HTML `<label>` Element.</span><span class="sxs-lookup"><span data-stu-id="1f971-179">Consider writing an HTML `<label>` element.</span></span> <span data-ttu-id="1f971-180">Sobald Sie eingeben `<l` in der Visual Studio-Editor zeigt IntelliSense übereinstimmenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="1f971-180">As soon as you enter `<l` in the Visual Studio editor, IntelliSense displays matching elements:</span></span>

![Bild](intro/_static/label.png)

<span data-ttu-id="1f971-182">Nicht nur erhalten Sie HTML-Hilfe, aber das Symbol "(dem" @"Symbolbreite"<>"darunter).</span><span class="sxs-lookup"><span data-stu-id="1f971-182">Not only do you get HTML help, but the icon (the "@" symbol with "<>" under it).</span></span>

![Bild](intro/_static/tagSym.png)

<span data-ttu-id="1f971-184">identifiziert das Element an, nach Tag Hilfsprogramme ausgerichtet sein.</span><span class="sxs-lookup"><span data-stu-id="1f971-184">identifies the element as targeted by Tag Helpers.</span></span> <span data-ttu-id="1f971-185">Reines HTML-Elemente (z. B. die `fieldset`) der "<>" Symbol "anzeigen".</span><span class="sxs-lookup"><span data-stu-id="1f971-185">Pure HTML elements (such as the `fieldset`) display the "<>" icon.</span></span>

<span data-ttu-id="1f971-186">Ein reines HTML `<label>` Tag zeigt das HTML-Tag (mit Visual Studio Farbe Standarddesign) in einer braunen Schriftart, die Attribute in Rot, und die Attributwerte in Blau dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1f971-186">A pure HTML `<label>` tag displays the HTML tag (with the default Visual Studio color theme) in a brown font, the attributes in red, and the attribute values in blue.</span></span>

![Bild](intro/_static/LableHtmlTag.png)

<span data-ttu-id="1f971-188">Nach der Eingabe `<label`, listet IntelliSense die verfügbaren Attribute für HTML/CSS und die Attribute Tag Helper dienenden:</span><span class="sxs-lookup"><span data-stu-id="1f971-188">After you enter `<label`, IntelliSense lists the available HTML/CSS attributes and the Tag Helper-targeted attributes:</span></span>

![Bild](intro/_static/labelattr.png)

<span data-ttu-id="1f971-190">IntelliSense-Anweisungsvervollständigung können Sie die Tab-Taste, um die Anweisung mit den ausgewählten Wert abzuschließen eingeben:</span><span class="sxs-lookup"><span data-stu-id="1f971-190">IntelliSense statement completion allows you to enter the tab key to complete the statement with the selected value:</span></span>

![Bild](intro/_static/stmtcomplete.png)

<span data-ttu-id="1f971-192">Als ein Tag Helper-Attribut eingegeben wird, ändern die Tag- und Schriftarten.</span><span class="sxs-lookup"><span data-stu-id="1f971-192">As soon as a Tag Helper attribute is entered, the tag and attribute fonts change.</span></span> <span data-ttu-id="1f971-193">Der standardmäßige Visual Studio "Blue" oder "Light" Farbschema verwenden, ist die Schriftart fett Lila.</span><span class="sxs-lookup"><span data-stu-id="1f971-193">Using the default Visual Studio "Blue" or "Light" color theme, the font is bold purple.</span></span> <span data-ttu-id="1f971-194">Bei Verwendung von "Dunklem" Design ist die Schriftart fett Blaugrün.</span><span class="sxs-lookup"><span data-stu-id="1f971-194">If you're using the "Dark" theme the font is bold teal.</span></span> <span data-ttu-id="1f971-195">Die Bilder in diesem Dokument durchgeführten verwenden das Standarddesign.</span><span class="sxs-lookup"><span data-stu-id="1f971-195">The images in this document were taken using the default theme.</span></span>

![Bild](intro/_static/labelaspfor2.png)

<span data-ttu-id="1f971-197">Können Sie die Visual Studio eingeben *CompleteWord* Verknüpfung (STRG + LEERTASTE ist die [Standard](https://msdn.microsoft.com/library/da5kh0wa.aspx)) innerhalb der doppelten Anführungszeichen (""), und Sie sind jetzt in C# geschrieben, wie Sie eine C#-Klasse wären.</span><span class="sxs-lookup"><span data-stu-id="1f971-197">You can enter the Visual Studio *CompleteWord* shortcut (Ctrl +spacebar is the [default](https://msdn.microsoft.com/library/da5kh0wa.aspx)) inside the double quotes (""), and you are now in C#, just like you would be in a C# class.</span></span> <span data-ttu-id="1f971-198">IntelliSense zeigt alle Methoden und Eigenschaften auf der Seite "-Modell an.</span><span class="sxs-lookup"><span data-stu-id="1f971-198">IntelliSense displays all the methods and properties on the page model.</span></span> <span data-ttu-id="1f971-199">Die Methoden und Eigenschaften sind verfügbar, weil der Eigenschaftstyp `ModelExpression`.</span><span class="sxs-lookup"><span data-stu-id="1f971-199">The methods and properties are available because the property type is `ModelExpression`.</span></span> <span data-ttu-id="1f971-200">In der folgenden Abbildung bin ich Bearbeiten der `Register` anzeigen, sodass der `RegisterViewModel` verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="1f971-200">In the image below, I'm editing the `Register` view, so the `RegisterViewModel` is available.</span></span>

![Bild](intro/_static/intellemail.png)

<span data-ttu-id="1f971-202">Die Eigenschaften und Methoden für das Modell auf der Seite, listet IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="1f971-202">IntelliSense lists the properties and methods available to the model on the page.</span></span> <span data-ttu-id="1f971-203">Die umfassende IntelliSense-Umgebung können Sie CSS-Klasse auswählen:</span><span class="sxs-lookup"><span data-stu-id="1f971-203">The rich IntelliSense environment helps you select the CSS class:</span></span>

![Bild](intro/_static/iclass.png)

![Bild](intro/_static/intel3.png)

## <a name="tag-helpers-compared-to-html-helpers"></a><span data-ttu-id="1f971-206">Tag-Hilfsprogramme, die im Vergleich zu HTML-Hilfsmethoden</span><span class="sxs-lookup"><span data-stu-id="1f971-206">Tag Helpers compared to HTML Helpers</span></span>

<span data-ttu-id="1f971-207">Tag-Hilfsprogrammen fügen Sie HTML-Elementen in Razor-Ansichten, während [HTML-Hilfsmethoden](http://stephenwalther.com/archive/2009/03/03/chapter-6-understanding-html-helpers) werden aufgerufen, wie Methoden mit HTML in Razor-Ansichten vermischt.</span><span class="sxs-lookup"><span data-stu-id="1f971-207">Tag Helpers attach to HTML elements in Razor views, while [HTML Helpers](http://stephenwalther.com/archive/2009/03/03/chapter-6-understanding-html-helpers) are invoked as methods interspersed with HTML in Razor views.</span></span> <span data-ttu-id="1f971-208">Betrachten Sie das folgende Razor-Markup, das eine HTML-Beschriftung mit dem CSS-Klasse "Caption" erstellt:</span><span class="sxs-lookup"><span data-stu-id="1f971-208">Consider the following Razor markup, which creates an HTML label with the CSS class "caption":</span></span>

```html
@Html.Label("FirstName", "First Name:", new {@class="caption"})
```

<span data-ttu-id="1f971-209">Die am (`@`) Symbol weist Razor Beginn des Codes sieht.</span><span class="sxs-lookup"><span data-stu-id="1f971-209">The at (`@`) symbol tells Razor this is the start of code.</span></span> <span data-ttu-id="1f971-210">Die nächsten zwei Parameter ("FirstName" und "First Name:") sind Zeichenfolgen, sodass [IntelliSense](https://msdn.microsoft.com/library/hcw1s69b.aspx) dabei nicht helfen kann.</span><span class="sxs-lookup"><span data-stu-id="1f971-210">The next two parameters ("FirstName" and "First Name:") are strings, so [IntelliSense](https://msdn.microsoft.com/library/hcw1s69b.aspx) can't help.</span></span> <span data-ttu-id="1f971-211">Das letzte Argument:</span><span class="sxs-lookup"><span data-stu-id="1f971-211">The last argument:</span></span>

```html
new {@class="caption"}
```

<span data-ttu-id="1f971-212">Ein anonymes Objekt wird zur Darstellung der Attribute verwendet.</span><span class="sxs-lookup"><span data-stu-id="1f971-212">Is an anonymous object used to represent attributes.</span></span> <span data-ttu-id="1f971-213">Da **Klasse** ist ein reserviertes Schlüsselwort in c#, verwenden Sie die `@` Symbol c# interpretieren erzwingen "@class=" als ein Symbol (Eigenschaftsnamen).</span><span data-stu-id="1f971-213">Because **class** is a reserved keyword in C#, you use the `@` symbol to force C# to interpret "@class=" as a symbol (property name).</span></span> <span data-ttu-id="1f971-214">Auf einem Front-End-Designer (eine Person mit HTML/CSS/JavaScript und anderen Clienttechnologien vertraut sind, aber nicht vertraut sind mit c# und Razor), ein Großteil der Linie ist foreign. <span data-ttu-id="1f971-215">Die gesamte Zeile muss mit der keine Unterstützung von IntelliSense erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="1f971-215">The entire line must be authored with no help from IntelliSense.</span></span>

<span data-ttu-id="1f971-216">Mithilfe der `LabelTagHelper`, als das gleiche Markup geschrieben werden kann:</span><span class="sxs-lookup"><span data-stu-id="1f971-216">Using the `LabelTagHelper`, the same markup can be written as:</span></span>

![Bild](intro/_static/label2.png)

<span data-ttu-id="1f971-218">Durch die Tag-Helper-Version, als Eingabe `<l` in der Visual Studio-Editor zeigt IntelliSense übereinstimmenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="1f971-218">With the Tag Helper version, as soon as you enter `<l` in the Visual Studio editor, IntelliSense displays matching elements:</span></span>

![Bild](intro/_static/label.png)

<span data-ttu-id="1f971-220">IntelliSense können Sie die gesamte Zeile zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="1f971-220">IntelliSense helps you write the entire line.</span></span> <span data-ttu-id="1f971-221">Die `LabelTagHelper` auch standardmäßig auf den Inhalt der Festlegen der `asp-for` -Attributwert ("FirstName") auf "Vorname"; Er konvertiert Camel-Case-Eigenschaften in einen Satz besteht aus den Namen der Eigenschaft mit einem Leerzeichen, in der jede neue Großbuchstaben auftritt.</span><span class="sxs-lookup"><span data-stu-id="1f971-221">The `LabelTagHelper` also defaults to setting the content of the `asp-for` attribute value ("FirstName") to "First Name"; It converts camel-cased properties to a sentence composed of the property name with a space where each new upper-case letter occurs.</span></span> <span data-ttu-id="1f971-222">Im folgenden Markup:</span><span class="sxs-lookup"><span data-stu-id="1f971-222">In the following markup:</span></span>

![Bild](intro/_static/label2.png)

<span data-ttu-id="1f971-224">generiert:</span><span class="sxs-lookup"><span data-stu-id="1f971-224">generates:</span></span>

```html
<label class="caption" for="FirstName">First Name</label>
```

<span data-ttu-id="1f971-225">Die in Kamel-Schreibweise Satz Schreibweise Inhalt wird nicht verwendet werden, wenn Sie Inhalt hinzuzufügen der `<label>`.</span><span class="sxs-lookup"><span data-stu-id="1f971-225">The camel-cased to sentence-cased content is not used if you add content to the `<label>`.</span></span> <span data-ttu-id="1f971-226">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f971-226">For example:</span></span>

![Bild](intro/_static/1stName.png)

<span data-ttu-id="1f971-228">generiert:</span><span class="sxs-lookup"><span data-stu-id="1f971-228">generates:</span></span>

```html
<label class="caption" for="FirstName">Name First</label>
```

<span data-ttu-id="1f971-229">Der folgende Code, Abbildung, des Formular-Teils der *Views/Account/Register.cshtml* Razor-Ansicht, die die ältere ASP.NET 4.5.x MVC-Vorlage mit Visual Studio 2015 enthalten generiert.</span><span class="sxs-lookup"><span data-stu-id="1f971-229">The following code image shows the Form portion of the *Views/Account/Register.cshtml* Razor view generated from the legacy ASP.NET 4.5.x MVC template included with Visual Studio 2015.</span></span>

![Bild](intro/_static/regCS.png)

<span data-ttu-id="1f971-231">Der Visual Studio-Editor zeigt C#-Code mit einem grauen Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="1f971-231">The Visual Studio editor displays C# code with a grey background.</span></span> <span data-ttu-id="1f971-232">Z. B. die `AntiForgeryToken` HTML-Hilfsobjekt:</span><span class="sxs-lookup"><span data-stu-id="1f971-232">For example, the `AntiForgeryToken` HTML Helper:</span></span>

```html
@Html.AntiForgeryToken()
```

<span data-ttu-id="1f971-233">wird mit einem grauen Hintergrund angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f971-233">is displayed with a grey background.</span></span> <span data-ttu-id="1f971-234">Die meisten das Markup in der Ansicht Register-ist c#.</span><span class="sxs-lookup"><span data-stu-id="1f971-234">Most of the markup in the Register view is C#.</span></span> <span data-ttu-id="1f971-235">Vergleichen Sie die entsprechende Ansatz bei Verwendung von Tag Hilfsprogramme:</span><span class="sxs-lookup"><span data-stu-id="1f971-235">Compare that to the equivalent approach using Tag Helpers:</span></span>

![Bild](intro/_static/regTH.png)

<span data-ttu-id="1f971-237">Das Markup ist wesentlich übersichtlichere und besser lesen, bearbeiten und verwalten als die HTML-Hilfsmethoden-Methode.</span><span class="sxs-lookup"><span data-stu-id="1f971-237">The markup is much cleaner and easier to read, edit, and maintain than the HTML Helpers approach.</span></span> <span data-ttu-id="1f971-238">Der C#-Code wird auf ein Minimum reduziert, die der Server benötigt, zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="1f971-238">The C# code is reduced to the minimum that the server needs to know about.</span></span> <span data-ttu-id="1f971-239">Der Visual Studio-Editor zeigt Markup, das Ziel eines Tag-Hilfsprogramms in eine besondere Schriftart an.</span><span class="sxs-lookup"><span data-stu-id="1f971-239">The Visual Studio editor displays markup targeted by a Tag Helper in a distinctive font.</span></span>

<span data-ttu-id="1f971-240">Betrachten Sie die *E-Mail* Gruppe:</span><span class="sxs-lookup"><span data-stu-id="1f971-240">Consider the *Email* group:</span></span>

<span data-ttu-id="1f971-241">[!code-csharp[Main](intro/sample/Register.cshtml?range=12-18)]</span><span class="sxs-lookup"><span data-stu-id="1f971-241">[!code-csharp[Main](intro/sample/Register.cshtml?range=12-18)]</span></span>

<span data-ttu-id="1f971-242">Jedes Attribut "Asp-" hat einen Wert von "Email", aber "Email" ist keine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1f971-242">Each of the "asp-" attributes has a value of "Email", but "Email" is not a string.</span></span> <span data-ttu-id="1f971-243">In diesem Kontext ist "Email" die C#-Modell Expression-Eigenschaft für die `RegisterViewModel`.</span><span class="sxs-lookup"><span data-stu-id="1f971-243">In this context, "Email" is the C# model expression property for the `RegisterViewModel`.</span></span>

<span data-ttu-id="1f971-244">Der Visual Studio-Editor unterstützt Sie beim Schreiben **alle** von Markup im Tag Helper Ansatz des Formulars registrieren, während Visual Studio keine Hilfe für den Großteil des Codes in der HTML-Hilfsmethoden Ansatz bietet.</span><span class="sxs-lookup"><span data-stu-id="1f971-244">The Visual Studio editor helps you write **all** of the markup in the Tag Helper approach of the register form, while Visual Studio provides no help for most of the code in the HTML Helpers approach.</span></span> <span data-ttu-id="1f971-245">[IntelliSense-Unterstützung für Tag Hilfsprogramme](#intellisense-support-for-tag-helpers) wechselt in Details zum Arbeiten mit Hilfsprogrammen Tag in der Visual Studio-Editor.</span><span class="sxs-lookup"><span data-stu-id="1f971-245">[IntelliSense support for Tag Helpers](#intellisense-support-for-tag-helpers) goes into detail on working with Tag Helpers in the Visual Studio editor.</span></span>

## <a name="tag-helpers-compared-to-web-server-controls"></a><span data-ttu-id="1f971-246">Tag-Hilfsprogramme, die im Vergleich zu Webserversteuerelemente</span><span class="sxs-lookup"><span data-stu-id="1f971-246">Tag Helpers compared to Web Server Controls</span></span>

* <span data-ttu-id="1f971-247">Tag-Hilfsprogrammen besitzen nicht das Element, denen, dem Sie zugeordnet sind; einfach beteiligt werden beim Rendern des Elements und Inhalt.</span><span class="sxs-lookup"><span data-stu-id="1f971-247">Tag Helpers don't own the element they're associated with; they simply participate in the rendering of the element and content.</span></span> <span data-ttu-id="1f971-248">ASP.NET [-Webserversteuerelemente](https://msdn.microsoft.com/library/7698y1f0.aspx) deklariert und auf einer Seite aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1f971-248">ASP.NET [Web Server controls](https://msdn.microsoft.com/library/7698y1f0.aspx) are declared and invoked on a page.</span></span>

* <span data-ttu-id="1f971-249">[-Webserversteuerelementen](https://msdn.microsoft.com/library/zsyt68f1.aspx) verfügen über einen nicht trivialen Lebenszyklus, die erschweren kann entwickeln und Debuggen.</span><span class="sxs-lookup"><span data-stu-id="1f971-249">[Web Server controls](https://msdn.microsoft.com/library/zsyt68f1.aspx) have a non-trivial lifecycle that can make developing and debugging difficult.</span></span>

* <span data-ttu-id="1f971-250">Webserversteuerelemente können Sie die Client-Elemente (DOKUMENTOBJEKTMODELL) mithilfe einer Clientsteuerelement Funktionen hinzu.</span><span class="sxs-lookup"><span data-stu-id="1f971-250">Web Server controls allow you to add functionality to the client Document Object Model (DOM) elements by using a client control.</span></span> <span data-ttu-id="1f971-251">Tag-Hilfsprogrammen haben keine DOM.</span><span class="sxs-lookup"><span data-stu-id="1f971-251">Tag Helpers have no DOM.</span></span>

* <span data-ttu-id="1f971-252">Webserversteuerelemente enthalten automatische Browsererkennung.</span><span class="sxs-lookup"><span data-stu-id="1f971-252">Web Server controls include automatic browser detection.</span></span> <span data-ttu-id="1f971-253">Tag-Hilfsprogrammen haben keine Kenntnis des Browsers.</span><span class="sxs-lookup"><span data-stu-id="1f971-253">Tag Helpers have no knowledge of the browser.</span></span>

* <span data-ttu-id="1f971-254">Können mehrere Tags Hilfen für dasselbe Element fungieren (finden Sie unter [Tag Helper Vermeiden von Konflikten](https://docs.microsoft.com/aspnet/core/mvc/views/tag-helpers/authoring#avoiding-tag-helper-conflicts) ), während Sie die Webserver-Steuerelemente in der Regel zusammenstellen können nicht.</span><span class="sxs-lookup"><span data-stu-id="1f971-254">Multiple Tag Helpers can act on the same element (see [Avoiding Tag Helper conflicts](https://docs.microsoft.com/aspnet/core/mvc/views/tag-helpers/authoring#avoiding-tag-helper-conflicts) ) while you typically can't compose Web Server controls.</span></span>

* <span data-ttu-id="1f971-255">Tag-Hilfsprogramme können ändern, den Tag und den Inhalt des HTML-Elemente, denen sie auf begrenzt sind, aber nicht direkt etwas anderes auf einer Seite ändern.</span><span class="sxs-lookup"><span data-stu-id="1f971-255">Tag Helpers can modify the tag and content of HTML elements that they're scoped to, but don't directly modify anything else on a page.</span></span> <span data-ttu-id="1f971-256">Webserversteuerelemente können verfügen über einen weniger spezifischen Bereich und Aktionen, die sich auf andere Teile der Seite; aktivieren dann unbeabsichtigte Nebeneffekte.</span><span class="sxs-lookup"><span data-stu-id="1f971-256">Web Server controls have a less specific scope and can perform actions that affect other parts of your page; enabling unintended side effects.</span></span>

* <span data-ttu-id="1f971-257">Webserversteuerelemente verwenden den Einsatz von Typkonvertern, um Zeichenfolgen in Objekte konvertieren.</span><span class="sxs-lookup"><span data-stu-id="1f971-257">Web Server controls use type converters to convert strings into objects.</span></span> <span data-ttu-id="1f971-258">Tag-Hilfen arbeiten Sie systemintern in c#, Sie müssen also keine Konvertierung eingeben.</span><span class="sxs-lookup"><span data-stu-id="1f971-258">With Tag Helpers, you work natively in C#, so you don't need to do type conversion.</span></span>

* <span data-ttu-id="1f971-259">Webserver-Steuerelemente verwenden [System.ComponentModel](https://msdn.microsoft.com/library/system.componentmodel%28v=vs.110%29.aspx) , das zur Laufzeit und Entwurfszeit Entwurfszeitverhalten von Komponenten und Steuerelementen implementieren.</span><span class="sxs-lookup"><span data-stu-id="1f971-259">Web Server controls use [System.ComponentModel](https://msdn.microsoft.com/library/system.componentmodel%28v=vs.110%29.aspx) to implement the run-time and design-time behavior of components and controls.</span></span> <span data-ttu-id="1f971-260">`System.ComponentModel`enthält die Basis-Klassen und Schnittstellen zum Implementieren von Attributen und den Einsatz von Typkonvertern, binden an Datenquellen und Lizenzieren von Komponenten.</span><span class="sxs-lookup"><span data-stu-id="1f971-260">`System.ComponentModel` includes the base classes and interfaces for implementing attributes and type converters, binding to data sources, and licensing components.</span></span> <span data-ttu-id="1f971-261">Im Gegensatz zum Tag-Hilfen, mit denen in der Regel abgeleitet `TagHelper`, und die `TagHelper` Basisklasse macht nur zwei Methoden `Process` und `ProcessAsync`.</span><span class="sxs-lookup"><span data-stu-id="1f971-261">Contrast that to Tag Helpers, which typically derive from `TagHelper`, and the `TagHelper` base class exposes only two methods, `Process` and `ProcessAsync`.</span></span>

## <a name="customizing-the-tag-helper-element-font"></a><span data-ttu-id="1f971-262">Anpassen der Schriftart-Element-Tag-Hilfsprogramm</span><span class="sxs-lookup"><span data-stu-id="1f971-262">Customizing the Tag Helper element font</span></span>

<span data-ttu-id="1f971-263">Sie können anpassen, die Schriftart und die farbliche Kennzeichnung von **Tools** > **Optionen** > **Umgebung** > **Schriftarten und Farben**:</span><span class="sxs-lookup"><span data-stu-id="1f971-263">You can customize the font and colorization from **Tools** > **Options** > **Environment** > **Fonts and Colors**:</span></span>

![Bild](intro/_static/fontoptions2.png)

## <a name="additional-resources"></a><span data-ttu-id="1f971-265">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="1f971-265">Additional Resources</span></span>

* [<span data-ttu-id="1f971-266">Erstellen von Tag-Hilfsprogramme</span><span class="sxs-lookup"><span data-stu-id="1f971-266">Authoring Tag Helpers</span></span>](authoring.md)
* [<span data-ttu-id="1f971-267">Arbeiten mit Formularen</span><span class="sxs-lookup"><span data-stu-id="1f971-267">Working with Forms </span></span>](../working-with-forms.md)
* <span data-ttu-id="1f971-268">[TagHelperSamples auf GitHub](https://github.com/dpaquette/TagHelperSamples) enthält Tag Helper-Beispiele für die Arbeit mit [Bootstrap](http://getbootstrap.com/).</span><span class="sxs-lookup"><span data-stu-id="1f971-268">[TagHelperSamples on GitHub](https://github.com/dpaquette/TagHelperSamples) contains Tag Helper samples for working with [Bootstrap](http://getbootstrap.com/).</span></span>

<!--
* [Working with Forms ](xref:mvc/views/working-with-forms)
-->