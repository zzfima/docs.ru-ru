---
title: Реализация классом XslTransform XSLT-процессора
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 88373fe2-4a6b-44f9-8a62-8a3e348e3a46
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 81d0ce4f697935908b8ad7084560bd1adacbdf2d
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44222731"
---
# <a name="xsltransform-class-implements-the-xslt-processor"></a><span data-ttu-id="d0f80-102">Реализация классом XslTransform XSLT-процессора</span><span class="sxs-lookup"><span data-stu-id="d0f80-102">XslTransform Class Implements the XSLT Processor</span></span>
> [!NOTE]
>  <span data-ttu-id="d0f80-103">Класс <xref:System.Xml.Xsl.XslTransform> в версии [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] устарел.</span><span class="sxs-lookup"><span data-stu-id="d0f80-103">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="d0f80-104">Можно выполнять XSLT-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="d0f80-104">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="d0f80-105">См. дополнительные сведения об [использовании класса XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) и [миграции из класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="d0f80-105">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="d0f80-106">Класс <xref:System.Xml.Xsl.XslTransform> является XSLT-процессором, реализующим рекомендации по XSL-преобразованиям (XSLT) версии 1.0.</span><span class="sxs-lookup"><span data-stu-id="d0f80-106">The <xref:System.Xml.Xsl.XslTransform> class is an XSLT processor implementing the XSL Transformations (XSLT) Version 1.0 recommendation.</span></span> <span data-ttu-id="d0f80-107">Метод <xref:System.Xml.Xsl.XslTransform.Load%2A> находит и считывает таблицы стилей, а метод <xref:System.Xml.Xsl.XslTransform.Transform%2A> преобразует исходный документ.</span><span class="sxs-lookup"><span data-stu-id="d0f80-107">The <xref:System.Xml.Xsl.XslTransform.Load%2A> method locates and reads style sheets, and the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method transforms the given source document.</span></span> <span data-ttu-id="d0f80-108">В качестве исходного документа для метода <xref:System.Xml.XPath.IXPathNavigable> может служить любое хранилище, реализующее интерфейс <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="d0f80-108">Any store that implements the <xref:System.Xml.XPath.IXPathNavigable> interface can be used as the source document for the <xref:System.Xml.Xsl.XslTransform>.</span></span> <span data-ttu-id="d0f80-109">Платформа [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] в настоящее время реализует интерфейс <xref:System.Xml.XPath.IXPathNavigable> в классах <xref:System.Xml.XmlDocument>, <xref:System.Xml.XmlDataDocument> и <xref:System.Xml.XPath.XPathDocument>, поэтому все они могут использоваться в качестве источника документов для преобразования.</span><span class="sxs-lookup"><span data-stu-id="d0f80-109">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] currently implements the <xref:System.Xml.XPath.IXPathNavigable> interface on the <xref:System.Xml.XmlDocument>, the <xref:System.Xml.XmlDataDocument>, and the <xref:System.Xml.XPath.XPathDocument>, so all of these can be used as the input source document to a transformation.</span></span>  
  
 <span data-ttu-id="d0f80-110">Объект <xref:System.Xml.Xsl.XslTransform> в платформе [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] поддерживает только спецификацию XSLT 1.0, определенную со следующим пространством имен:</span><span class="sxs-lookup"><span data-stu-id="d0f80-110">The <xref:System.Xml.Xsl.XslTransform> object in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] only supports the XSLT 1.0 specification, defined with the following namespace:</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">    
```  
  
 <span data-ttu-id="d0f80-111">Загрузить таблицу стилей можно, вызвав метод <xref:System.Xml.Xsl.XslTransform.Load%2A> из одного из следующих классов:</span><span class="sxs-lookup"><span data-stu-id="d0f80-111">The style sheet can be loaded, using the <xref:System.Xml.Xsl.XslTransform.Load%2A> method, from one of the following classes:</span></span>  
  
-   <span data-ttu-id="d0f80-112">XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="d0f80-112">XPathNavigator</span></span>  
  
-   <span data-ttu-id="d0f80-113">XmlReader</span><span class="sxs-lookup"><span data-stu-id="d0f80-113">XmlReader</span></span>  
  
-   <span data-ttu-id="d0f80-114">Строка, представляющая URL-адрес</span><span class="sxs-lookup"><span data-stu-id="d0f80-114">A string representing a URL</span></span>  
  
 <span data-ttu-id="d0f80-115">Существует другой метод <xref:System.Xml.Xsl.XslTransform.Load%2A> для каждого из приведенных выше входных классов.</span><span class="sxs-lookup"><span data-stu-id="d0f80-115">There is a different <xref:System.Xml.Xsl.XslTransform.Load%2A> method for each of the above input classes.</span></span> <span data-ttu-id="d0f80-116">Некоторые методы принимают в качестве аргументов сочетание одного из этих классов и класса <xref:System.Xml.XmlResolver>.</span><span class="sxs-lookup"><span data-stu-id="d0f80-116">Some methods take in a combination of one of these classes and the <xref:System.Xml.XmlResolver> class as arguments.</span></span> <span data-ttu-id="d0f80-117">Класс <xref:System.Xml.XmlResolver> находит ресурсы, на которые ссылаются элементы `<xsl:import>` или `<xsl:include>` в таблице стилей.</span><span class="sxs-lookup"><span data-stu-id="d0f80-117">The <xref:System.Xml.XmlResolver> locates resources referenced by `<xsl:import>` or `<xsl:include>` found in the style sheet.</span></span> <span data-ttu-id="d0f80-118">Следующие методы в качестве входного значения принимают строку: <xref:System.Xml.XmlReader> и <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="d0f80-118">The following methods take a string, <xref:System.Xml.XmlReader>, or <xref:System.Xml.XPath.XPathNavigator> as input.</span></span>  
  
```vb  
Overloads Public Sub Load(String)  
```  
  
```csharp  
public void Load(string);  
```  
  
```vb  
Overloads Public Sub Load(String, XmlResolver)  
```  
  
```csharp  
public void Load(string, XmlResolver);  
```  
  
```vb  
Overloads Public Sub Load(XmlReader, XmlResolver, Evidence)  
```  
  
```csharp  
public void Load(XmlReader, XmlResolver, Evidence);  
```  
  
```vb  
Overloads Public Sub Load(XPathNavigator, XmlResolver, Evidence)  
```  
  
```csharp  
public void Load(XPathNavigator, XmlResolver, Evidence);  
```  
  
 <span data-ttu-id="d0f80-119">Большая часть приведенных выше методов <xref:System.Xml.Xsl.XslTransform.Load%2A> принимает в качестве параметра объект <xref:System.Xml.XmlResolver>.</span><span class="sxs-lookup"><span data-stu-id="d0f80-119">Most of the <xref:System.Xml.Xsl.XslTransform.Load%2A> methods shown above take an <xref:System.Xml.XmlResolver> as a parameter.</span></span> <span data-ttu-id="d0f80-120">Объект <xref:System.Xml.XmlResolver> используется для загрузки таблицы стилей и всех таблиц стилей, на которые имеются ссылки в элементах xsl:import и xsl:include.</span><span class="sxs-lookup"><span data-stu-id="d0f80-120">The <xref:System.Xml.XmlResolver> is used to load the style sheet and any style sheet(s) referenced in xsl:import and xsl:include elements.</span></span>  
  
 <span data-ttu-id="d0f80-121">Большинство методов <xref:System.Xml.Xsl.XslTransform.Load%2A> также принимает свидетельство в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="d0f80-121">Most of the <xref:System.Xml.Xsl.XslTransform.Load%2A> methods also take evidence as a parameter.</span></span> <span data-ttu-id="d0f80-122">Параметр-свидетельство является объектом <xref:System.Security.Policy.Evidence>, связанным с таблицей стилей.</span><span class="sxs-lookup"><span data-stu-id="d0f80-122">The evidence parameter is the <xref:System.Security.Policy.Evidence> that is associated with the style sheet.</span></span> <span data-ttu-id="d0f80-123">Уровень безопасности таблицы стилей влияет на уровень безопасности всех последующих ресурсов, на которые она ссылается, например содержащийся в ней скрипт, все вызываемые функции `document()` и все объекты расширения, используемые объектом <xref:System.Xml.Xsl.XsltArgumentList>.</span><span class="sxs-lookup"><span data-stu-id="d0f80-123">The security level of the style sheet affects the security level of any subsequent resources it references, such as the script it contains, any `document()` functions it uses, and any extension objects used by the <xref:System.Xml.Xsl.XsltArgumentList>.</span></span>  
  
 <span data-ttu-id="d0f80-124">Если таблица стилей загружается с помощью метода <xref:System.Xml.Xsl.XslTransform.Load%2A>, содержащего параметр URL-адреса и не содержащего свидетельства, свидетельство таблицы стилей вычисляется путем объединения этого URL-адреса с его веб-узлом и зоной.</span><span class="sxs-lookup"><span data-stu-id="d0f80-124">If the style sheet is loaded using a <xref:System.Xml.Xsl.XslTransform.Load%2A> method that contains a URL parameter and no evidence is provided, the evidence of the style sheet is calculated by combining the given URL with its site and zone.</span></span>  
  
 <span data-ttu-id="d0f80-125">Если URI или свидетельство отсутствуют, то свидетельство таблицы стилей считается полностью доверенным.</span><span class="sxs-lookup"><span data-stu-id="d0f80-125">If no URI or evidence is provided, then the evidence set for the style sheet is fully trusted.</span></span> <span data-ttu-id="d0f80-126">Не загружайте таблицы стилей из ненадежных источников и не добавляйте ненадежные объекты расширения в объект <xref:System.Xml.Xsl.XsltArgumentList>.</span><span class="sxs-lookup"><span data-stu-id="d0f80-126">Do not load style sheets from untrusted sources, or add untrusted extension objects into the <xref:System.Xml.Xsl.XsltArgumentList>.</span></span>  
  
 <span data-ttu-id="d0f80-127">Дополнительные сведения об уровнях безопасности и свидетельстве, а также об их влиянии на работу со скриптами, вы найдете в статье [о скриптах для таблиц стилей XSLT с использованием \<msxsl:script>](../../../../docs/standard/data/xml/xslt-stylesheet-scripting-using-msxsl-script.md).</span><span class="sxs-lookup"><span data-stu-id="d0f80-127">For more information about security levels and evidence and how it affects scripting, see [XSLT Stylesheet Scripting Using \<msxsl:script>](../../../../docs/standard/data/xml/xslt-stylesheet-scripting-using-msxsl-script.md).</span></span> <span data-ttu-id="d0f80-128">Сведения об уровнях безопасности и свидетельстве, а также об их влиянии на объекты расширения см. в статье [XsltArgumentList для параметров таблицы стилей и объектов расширения](../../../../docs/standard/data/xml/xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md).</span><span class="sxs-lookup"><span data-stu-id="d0f80-128">For information about security levels and evidence and how it affects extension objects, see [XsltArgumentList for Style Sheet Parameters and Extension Objects](../../../../docs/standard/data/xml/xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md).</span></span>  
  
 <span data-ttu-id="d0f80-129">Сведения об уровнях безопасности и свидетельстве, а также об их влиянии на функцию `document()` см. в статье [Разрешение внешних таблиц стилей XSLT и документов](../../../../docs/standard/data/xml/resolving-external-xslt-style-sheets-and-documents.md).</span><span class="sxs-lookup"><span data-stu-id="d0f80-129">For information about security levels and evidence and how it affects the `document()` function, see [Resolving External XSLT Style Sheets and Documents](../../../../docs/standard/data/xml/resolving-external-xslt-style-sheets-and-documents.md).</span></span>  
  
 <span data-ttu-id="d0f80-130">Таблицу стилей можно предоставить с рядом входных параметров.</span><span class="sxs-lookup"><span data-stu-id="d0f80-130">A style sheet can be supplied with a number of input parameters.</span></span> <span data-ttu-id="d0f80-131">Таблица стилей может также вызывать функции в объектах расширения.</span><span class="sxs-lookup"><span data-stu-id="d0f80-131">The style sheet can also call functions on extension objects.</span></span> <span data-ttu-id="d0f80-132">Как параметры, так и объекты расширения предоставляются таблице стилей с помощью объекта <xref:System.Xml.Xsl.XsltArgumentList>.</span><span class="sxs-lookup"><span data-stu-id="d0f80-132">Both parameters and extension objects are supplied to the style sheet using the <xref:System.Xml.Xsl.XsltArgumentList> class.</span></span> <span data-ttu-id="d0f80-133">Дополнительные сведения о веб-службе <xref:System.Xml.Xsl.XsltArgumentList> см. в разделе <xref:System.Xml.Xsl.XsltArgumentList>.</span><span class="sxs-lookup"><span data-stu-id="d0f80-133">For more information about the <xref:System.Xml.Xsl.XsltArgumentList>, see <xref:System.Xml.Xsl.XsltArgumentList>.</span></span>  
  
## <a name="recommended-secure-use-of-xsltransform-class"></a><span data-ttu-id="d0f80-134">Рекомендованное безопасное использование класса XslTransform</span><span class="sxs-lookup"><span data-stu-id="d0f80-134">Recommended Secure Use of XslTransform Class</span></span>  
 <span data-ttu-id="d0f80-135">Права доступа таблицы стилей зависят от предоставленного свидетельства.</span><span class="sxs-lookup"><span data-stu-id="d0f80-135">The security privileges of the style sheet depend on the evidence provided.</span></span> <span data-ttu-id="d0f80-136">В следующей таблице представлено расположение таблицы стилей и объясняется соответствующий тип свидетельства.</span><span class="sxs-lookup"><span data-stu-id="d0f80-136">The following table summarizes the location of the style sheet and gives an explanation of what type of evidence to give.</span></span>  
  
-   <span data-ttu-id="d0f80-137">Таблица стилей XSLT не имеет внешних ссылок или поступает из доверенного кода.</span><span class="sxs-lookup"><span data-stu-id="d0f80-137">The XSLT style sheet has no external references, or the style sheet comes from a code base that you trust.</span></span>  
  
    -   <span data-ttu-id="d0f80-138">Предоставьте свидетельство из собственной сборки:</span><span class="sxs-lookup"><span data-stu-id="d0f80-138">Provide the evidence from your assembly:</span></span>  
  
         `Dim xslt = New XslTransform() xslt.Load(stylesheet, resolver, Me.GetType().Assembly.Evidence)`  
  
         `XsltTransform xslt = new XslTransform();  xslt.Load(stylesheet, resolver, this.GetType().Assembly.Evidence);`  
  
-   <span data-ttu-id="d0f80-139">Таблица стилей XSLT поступает из внешнего источника.</span><span class="sxs-lookup"><span data-stu-id="d0f80-139">The XSLT style sheet comes from an outside source.</span></span> <span data-ttu-id="d0f80-140">Происхождение источника известно, существует поддающийся проверке URI.</span><span class="sxs-lookup"><span data-stu-id="d0f80-140">The origin of the source is known and there is a verifiable URI.</span></span>  
  
    -   <span data-ttu-id="d0f80-141">Создайте свидетельство с помощью этого URI.</span><span class="sxs-lookup"><span data-stu-id="d0f80-141">Create evidence using the URI.</span></span>  
  
         `Dim xslt As New XslTransform() Dim ev As Evidence = XmlSecureResolver.CreateEvidenceForUrl(stylesheetUri) xslt.Load(stylesheet, resolver, evidence)`  
  
         `XslTransform xslt = new XslTransform(); Evidence ev = XmlSecureResolver.CreateEvidenceForUrl(stylesheetUri); xslt.Load(stylesheet, resolver, evidence);`  
  
-   <span data-ttu-id="d0f80-142">Таблица стилей XSLT поступает из внешнего источника.</span><span class="sxs-lookup"><span data-stu-id="d0f80-142">The XSLT style sheet comes from an outside source.</span></span> <span data-ttu-id="d0f80-143">Происхождение источника неизвестно.</span><span class="sxs-lookup"><span data-stu-id="d0f80-143">The origin of the source is not known.</span></span>  
  
    -   <span data-ttu-id="d0f80-144">Присвойте свидетельству значение `null`.</span><span class="sxs-lookup"><span data-stu-id="d0f80-144">Set evidence to `null`.</span></span> <span data-ttu-id="d0f80-145">Блоки скриптов не обрабатываются, функция XSLT `document()` не поддерживается, привилегированные объекты расширения запрещены.</span><span class="sxs-lookup"><span data-stu-id="d0f80-145">Script blocks are not processed, the XSLT `document()` function is not supported, and privileged extension objects are disallowed.</span></span>  
  
         <span data-ttu-id="d0f80-146">Кроме того, можно также присвоить параметру `resolver` значение `null`. Это гарантирует, что элементы `xsl:import` и `xsl:include` не будут обрабатываться.</span><span class="sxs-lookup"><span data-stu-id="d0f80-146">Additionally, you can also set the `resolver` parameter to `null` This ensures that `xsl:import` and `xsl:include` elements are not processed.</span></span>  
  
-   <span data-ttu-id="d0f80-147">Таблица стилей XSLT поступает из внешнего источника.</span><span class="sxs-lookup"><span data-stu-id="d0f80-147">The XSLT style sheet comes from an outside source.</span></span> <span data-ttu-id="d0f80-148">Происхождение источника неизвестно, но необходима поддержка скриптов.</span><span class="sxs-lookup"><span data-stu-id="d0f80-148">The origin of the source is not known, but you require script support.</span></span>  
  
    -   <span data-ttu-id="d0f80-149">Запросите свидетельство у вызывающего.</span><span class="sxs-lookup"><span data-stu-id="d0f80-149">Request evidence from the caller.</span></span>  
  
## <a name="transformation-of-xml-data"></a><span data-ttu-id="d0f80-150">Преобразование XML-данных</span><span class="sxs-lookup"><span data-stu-id="d0f80-150">Transformation of XML Data</span></span>  
 <span data-ttu-id="d0f80-151">После загрузки таблицы стилей преобразование начинается с вызова методов <xref:System.Xml.Xsl.XslTransform.Transform%2A> и предоставления исходного документа источника.</span><span class="sxs-lookup"><span data-stu-id="d0f80-151">Once a style sheet is loaded, the transformation starts by calling one of the <xref:System.Xml.Xsl.XslTransform.Transform%2A> methods and supplying an input source document.</span></span> <span data-ttu-id="d0f80-152">Метод <xref:System.Xml.Xsl.XslTransform.Transform%2A> перегружен, чтобы обеспечить разные выходные данные преобразования.</span><span class="sxs-lookup"><span data-stu-id="d0f80-152">The <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is overloaded to provide different transformation outputs.</span></span> <span data-ttu-id="d0f80-153">Преобразование может завершиться следующими выходными форматами:</span><span class="sxs-lookup"><span data-stu-id="d0f80-153">The transformation can result in the following output formats:</span></span>  
  
-   <xref:System.Xml.XmlReader>  
  
-   <xref:System.Xml.XmlWriter>  
  
-   <xref:System.IO.TextWriter>  
  
-   <xref:System.IO.Stream>  
  
-   <span data-ttu-id="d0f80-154">Строковый URL-адрес файла</span><span class="sxs-lookup"><span data-stu-id="d0f80-154">String URL of file</span></span>  
  
 <span data-ttu-id="d0f80-155">Последний формат, строковый URL-адрес файла, является наиболее распространенной ситуацией при преобразовании исходного документа, находящегося по определенному URL-адресу, и записи этого документа в выходной URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="d0f80-155">This last format, the string URL, provides for a commonly used scenario in transforming an input document located in a URL and writing the document to the output URL.</span></span> <span data-ttu-id="d0f80-156">Метод <xref:System.Xml.Xsl.XslTransform.Transform%2A> является самым удобным для загрузки XML-документа из файла, выполнения XSLT-преобразования и записи выходных данных в файл.</span><span class="sxs-lookup"><span data-stu-id="d0f80-156">This <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is a convenience method to load an XML document from a file, perform the XSLT transformation, and write the output to a file.</span></span> <span data-ttu-id="d0f80-157">При этом не нужно создавать и загружать исходный документ с последующей записью в файловый поток.</span><span class="sxs-lookup"><span data-stu-id="d0f80-157">This prevents you from having to create and load the input source document, and then write to a file stream.</span></span> <span data-ttu-id="d0f80-158">В следующем образце кода показано применение метода <xref:System.Xml.Xsl.XslTransform.Transform%2A> при использовании строкового URL-адреса в качестве входных и выходных данных:</span><span class="sxs-lookup"><span data-stu-id="d0f80-158">The following code sample shows this use of the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method using the string URL as input and output:</span></span>  
  
```vb  
Dim xsltransform As XslTransform = New XslTransform()  
xsltransform.Load("favorite.xsl")  
xsltransform.Transform("MyDocument.Xml", "TransformResult.xml", Nothing)  
```  
  
```csharp  
XslTransform xsltransform = new XslTransform();  
xsltransform.Load("favorite.xsl");  
xsltransform.Transform("MyDocument.xml", "TransformResult.xml", null);  
```  
  
## <a name="transforming-a-section-of-an-xml-document"></a><span data-ttu-id="d0f80-159">Преобразование раздела XML-документа</span><span class="sxs-lookup"><span data-stu-id="d0f80-159">Transforming a Section of an XML Document</span></span>  
 <span data-ttu-id="d0f80-160">Преобразования применяются к документу в целом.</span><span class="sxs-lookup"><span data-stu-id="d0f80-160">Transformations apply to the document as a whole.</span></span> <span data-ttu-id="d0f80-161">Иными словами, если передать узел, отличный от корневого узла документа, это не помешает процессу преобразования обратиться ко всем узлам загружаемого документа.</span><span class="sxs-lookup"><span data-stu-id="d0f80-161">In other words, if you pass in a node other than the document root node, this does not prevent the transformation process from accessing all nodes in the loaded document.</span></span> <span data-ttu-id="d0f80-162">Чтобы преобразовать фрагмент результирующего дерева, необходимо создать объект <xref:System.Xml.XmlDocument>, содержащий только фрагмент результирующего дерева, и передать этот объект <xref:System.Xml.XmlDocument> методу <xref:System.Xml.Xsl.XslTransform.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="d0f80-162">To transform a result tree fragment, you must create an <xref:System.Xml.XmlDocument> containing just the result tree fragment and pass that <xref:System.Xml.XmlDocument> to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method.</span></span> <span data-ttu-id="d0f80-163">В следующем примере выполняется преобразование фрагмента результирующего дерева.</span><span class="sxs-lookup"><span data-stu-id="d0f80-163">The following example performs a transformation on a result tree fragment.</span></span>  
  
```vb  
Dim xslt As New XslTransform()  
xslt.Load("print_root.xsl")  
Dim doc As New XmlDocument()  
doc.Load("library.xml")  
' Create a new document containing just the result tree fragment.  
Dim testNode As XmlNode = doc.DocumentElement.FirstChild  
Dim tmpDoc As New XmlDocument()  
tmpDoc.LoadXml(testNode.OuterXml)  
' Pass the document containing the result tree fragment   
' to the Transform method.  
Console.WriteLine(("Passing " + tmpDoc.OuterXml + " to print_root.xsl"))  
xslt.Transform(tmpDoc, Nothing, Console.Out, Nothing)  
```  
  
```csharp  
XslTransform xslt = new XslTransform();       
xslt.Load("print_root.xsl");  
XmlDocument doc = new XmlDocument();  
doc.Load("library.xml");  
// Create a new document containing just the result tree fragment.  
XmlNode testNode = doc.DocumentElement.FirstChild;   
XmlDocument tmpDoc = new XmlDocument();   
tmpDoc.LoadXml(testNode.OuterXml);  
// Pass the document containing the result tree fragment   
// to the Transform method.  
Console.WriteLine("Passing " + tmpDoc.OuterXml + " to print_root.xsl");  
xslt.Transform(tmpDoc, null, Console.Out, null);  
```  
  
 <span data-ttu-id="d0f80-164">Пример использует в качестве входных данных файлы library.xml и print_root.xsl и выводит на консоль следующее:</span><span class="sxs-lookup"><span data-stu-id="d0f80-164">The example uses the library.xml and print_root.xsl files as input and outputs the following to the console.</span></span>  
  
```  
Passing <book genre="novel" ISBN="1-861001-57-5"><title>Pride And Prejudice</title></book> to print_root.xsl   
Root node is book.  
```  
  
 <span data-ttu-id="d0f80-165">library.xml</span><span class="sxs-lookup"><span data-stu-id="d0f80-165">library.xml</span></span>  
  
```xml  
<library>  
  <book genre='novel' ISBN='1-861001-57-5'>  
     <title>Pride And Prejudice</title>  
  </book>  
  <book genre='novel' ISBN='1-81920-21-2'>  
     <title>Hook</title>  
  </book>  
</library>  
```  
  
 <span data-ttu-id="d0f80-166">print_root.xsl</span><span class="sxs-lookup"><span data-stu-id="d0f80-166">print_root.xsl</span></span>  
  
```xml  
<stylesheet version="1.0" xmlns="http://www.w3.org/1999/XSL/Transform" >  
  <output method="text" />   
  <template match="/">  
     Root node is  <value-of select="local-name(//*[position() = 1])" />   
  </template>  
</stylesheet>  
```  
  
## <a name="migration-of-xslt-from-net-framework-version-10-to-net-framework-version-11"></a><span data-ttu-id="d0f80-167">Миграция XSLT с платформы .NET Framework версии 1.0 на платформу .NET Framework версии 1.1</span><span class="sxs-lookup"><span data-stu-id="d0f80-167">Migration of XSLT from .NET Framework version 1.0 to .NET Framework version 1.1</span></span>  
 <span data-ttu-id="d0f80-168">В следующей таблице показаны устаревшие методы платформы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.0 и новые методы платформы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.1 для метода <xref:System.Xml.Xsl.XslTransform.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="d0f80-168">The following table shows the obsolete [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] version 1.0 methods and new [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] version 1.1 methods for the <xref:System.Xml.Xsl.XslTransform.Load%2A> method.</span></span> <span data-ttu-id="d0f80-169">Новые методы позволяют ограничить разрешения таблицы стилей, указывая свидетельство.</span><span class="sxs-lookup"><span data-stu-id="d0f80-169">The new methods enable you to limit the permissions of the style sheet by specifying evidence.</span></span>  
  
|<span data-ttu-id="d0f80-170">Устаревшие методы Load платформы .NET Framework версии 1.0</span><span class="sxs-lookup"><span data-stu-id="d0f80-170">Obsolete .NET Framework version 1.0 Load Methods</span></span>|<span data-ttu-id="d0f80-171">Заменяющие их методы Load платформы .NET Framework версии 1.1</span><span class="sxs-lookup"><span data-stu-id="d0f80-171">Replacement .NET Framework version 1.1 Load Methods</span></span>|  
|------------------------------------------------------|---------------------------------------------------------|  
|<span data-ttu-id="d0f80-172">Load(XPathNavigator input);</span><span class="sxs-lookup"><span data-stu-id="d0f80-172">Load(XPathNavigator input);</span></span><br /><br /> <span data-ttu-id="d0f80-173">Load(XPathNavigator input, XmlResolver resolver);</span><span class="sxs-lookup"><span data-stu-id="d0f80-173">Load(XPathNavigator input, XmlResolver resolver);</span></span>|<span data-ttu-id="d0f80-174">Load(XPathNavigator stylesheet, XmlResolver resolver, Evidence evidence);</span><span class="sxs-lookup"><span data-stu-id="d0f80-174">Load(XPathNavigator stylesheet, XmlResolver resolver, Evidence evidence);</span></span>|  
|<span data-ttu-id="d0f80-175">Load(IXPathNavigable stylesheet);</span><span class="sxs-lookup"><span data-stu-id="d0f80-175">Load(IXPathNavigable stylesheet);</span></span><br /><br /> <span data-ttu-id="d0f80-176">Load(IXPathNavigable stylesheet, XmlResolver resolver);</span><span class="sxs-lookup"><span data-stu-id="d0f80-176">Load(IXPathNavigable stylesheet, XmlResolver resolver);</span></span>|<span data-ttu-id="d0f80-177">Load(IXPathNavigable stylesheet, XmlResolver resolver, Evidence evidence);</span><span class="sxs-lookup"><span data-stu-id="d0f80-177">Load(IXPathNavigable stylesheet, XmlResolver resolver, Evidence evidence);</span></span>|  
|<span data-ttu-id="d0f80-178">Load(XmlReader stylesheet);</span><span class="sxs-lookup"><span data-stu-id="d0f80-178">Load(XmlReader stylesheet);</span></span><br /><br /> <span data-ttu-id="d0f80-179">Load(XmlReader stylesheet, XmlResolver resolver);</span><span class="sxs-lookup"><span data-stu-id="d0f80-179">Load(XmlReader stylesheet, XmlResolver resolver);</span></span>|<span data-ttu-id="d0f80-180">Load(XmlReader stylesheet, XmlResolver resolver, Evidence evidence);</span><span class="sxs-lookup"><span data-stu-id="d0f80-180">Load(XmlReader stylesheet, XmlResolver resolver, Evidence evidence);</span></span>|  
  
 <span data-ttu-id="d0f80-181">В следующей таблице показаны устаревшие и новые методы для метода <xref:System.Xml.Xsl.XslTransform.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="d0f80-181">The following table shows the obsolete and new methods for the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method.</span></span> <span data-ttu-id="d0f80-182">Новые методы принимают объект <xref:System.Xml.XmlResolver>.</span><span class="sxs-lookup"><span data-stu-id="d0f80-182">The new methods take an <xref:System.Xml.XmlResolver> object.</span></span>  
  
|<span data-ttu-id="d0f80-183">Устаревшие методы Transform платформы .NET Framework версии 1.0</span><span class="sxs-lookup"><span data-stu-id="d0f80-183">Obsolete .NET Framework version 1.0 Transform Methods</span></span>|<span data-ttu-id="d0f80-184">Заменяющие их методы Transform платформы .NET Framework версии 1.1</span><span class="sxs-lookup"><span data-stu-id="d0f80-184">Replacement .NET Framework version Transform 1.1 Methods</span></span>|  
|-----------------------------------------------------------|--------------------------------------------------------------|  
|<span data-ttu-id="d0f80-185">XmlReader Transform(XPathNavigator input, XsltArgumentList args)</span><span class="sxs-lookup"><span data-stu-id="d0f80-185">XmlReader Transform(XPathNavigator input, XsltArgumentList args)</span></span>|<span data-ttu-id="d0f80-186">XmlReader Transform(XPathNavigator  input, XsltArgumentList args, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="d0f80-186">XmlReader Transform(XPathNavigator  input, XsltArgumentList args, XmlResolver resolver)</span></span>|  
|<span data-ttu-id="d0f80-187">XmlReader Transform(IXPathNavigable input, XsltArgumentList args)</span><span class="sxs-lookup"><span data-stu-id="d0f80-187">XmlReader Transform(IXPathNavigable input, XsltArgumentList args)</span></span>|<span data-ttu-id="d0f80-188">XmlReader Transform(IXPathNavigable input, XsltArgumentList args, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="d0f80-188">XmlReader Transform(IXPathNavigable input, XsltArgumentList args, XmlResolver resolver)</span></span>|  
|<span data-ttu-id="d0f80-189">Void Transform(XPathNavigator input, XsltArgumentList args, XmlWriter output)</span><span class="sxs-lookup"><span data-stu-id="d0f80-189">Void Transform(XPathNavigator input, XsltArgumentList args, XmlWriter output)</span></span>|<span data-ttu-id="d0f80-190">Void Transform(XPathNavigator input, XsltArgumentList args, XmlWriter output, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="d0f80-190">Void Transform(XPathNavigator input, XsltArgumentList args, XmlWriter output, XmlResolver resolver)</span></span>|  
|<span data-ttu-id="d0f80-191">Void Transform(IXPathNavigable input, XsltArgumentList args, XmlWriter output)</span><span class="sxs-lookup"><span data-stu-id="d0f80-191">Void Transform(IXPathNavigable input, XsltArgumentList args, XmlWriter output)</span></span>|<span data-ttu-id="d0f80-192">Void Transform(IXpathNavigable input, XsltArgumentList args, XmlWriter output, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="d0f80-192">Void Transform(IXpathNavigable input, XsltArgumentList args, XmlWriter output, XmlResolver resolver)</span></span>|  
|<span data-ttu-id="d0f80-193">Void Transform(XPathNavigator input, XsltArgumentList args, TextWriter output)</span><span class="sxs-lookup"><span data-stu-id="d0f80-193">Void Transform(XPathNavigator input, XsltArgumentList args, TextWriter output)</span></span>|<span data-ttu-id="d0f80-194">Void Transform(XPathNavigator input, XsltArgumentList args, TextWriter output, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="d0f80-194">Void Transform(XPathNavigator input, XsltArgumentList args, TextWriter output, XmlResolver resolver)</span></span>|  
|<span data-ttu-id="d0f80-195">Void Transform(IXPathNavigable input, XsltArgumentList args, TextWriter output)</span><span class="sxs-lookup"><span data-stu-id="d0f80-195">Void Transform(IXPathNavigable input, XsltArgumentList args, TextWriter output)</span></span>|<span data-ttu-id="d0f80-196">Void Transform(IXPathNavigable input, XsltArgumentList args, TextWriter output, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="d0f80-196">Void Transform(IXPathNavigable input, XsltArgumentList args, TextWriter output, XmlResolver resolver)</span></span>|  
|<span data-ttu-id="d0f80-197">Void Transform(XPathNavigator input, XsltArgumentList args, Stream output)</span><span class="sxs-lookup"><span data-stu-id="d0f80-197">Void Transform(XPathNavigator input, XsltArgumentList args, Stream output)</span></span>|<span data-ttu-id="d0f80-198">Void Transform(XPathNavigator input, XsltArgumentList args, Stream output, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="d0f80-198">Void Transform(XPathNavigator input, XsltArgumentList args, Stream output, XmlResolver resolver)</span></span>|  
|<span data-ttu-id="d0f80-199">Void Transform(IXPathNavigable input, XsltArgumentList args, Stream output)</span><span class="sxs-lookup"><span data-stu-id="d0f80-199">Void Transform(IXPathNavigable input, XsltArgumentList args, Stream output)</span></span>|<span data-ttu-id="d0f80-200">Void Transform(IXPathNavigable input, XsltArgumentList args, Stream output, XmlResolver resolver)</span><span class="sxs-lookup"><span data-stu-id="d0f80-200">Void Transform(IXPathNavigable input, XsltArgumentList args, Stream output, XmlResolver resolver)</span></span>|  
|<span data-ttu-id="d0f80-201">Void Transform(String input, String output);</span><span class="sxs-lookup"><span data-stu-id="d0f80-201">Void Transform(String input, String output);</span></span>|<span data-ttu-id="d0f80-202">Void Transform(String input, String output, XmlResolver resolver);</span><span class="sxs-lookup"><span data-stu-id="d0f80-202">Void Transform(String input, String output, XmlResolver resolver);</span></span>|  
  
 <span data-ttu-id="d0f80-203">Свойство <xref:System.Xml.Xsl.XslTransform.XmlResolver%2A?displayProperty=nameWithType> устарело в платформе [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.1.</span><span class="sxs-lookup"><span data-stu-id="d0f80-203">The <xref:System.Xml.Xsl.XslTransform.XmlResolver%2A?displayProperty=nameWithType> property is obsolete in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] version 1.1.</span></span> <span data-ttu-id="d0f80-204">Используйте вместо него новые перегрузки <xref:System.Xml.Xsl.XslTransform.Transform%2A>, принимающие объект <xref:System.Xml.XmlResolver>.</span><span class="sxs-lookup"><span data-stu-id="d0f80-204">Instead, use the new <xref:System.Xml.Xsl.XslTransform.Transform%2A> overloads which take an <xref:System.Xml.XmlResolver> object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0f80-205">См. также</span><span class="sxs-lookup"><span data-stu-id="d0f80-205">See also</span></span>

- <xref:System.Xml.Xsl.XslTransform>  
- [<span data-ttu-id="d0f80-206">XSLT-преобразования с помощью класса XslTransform</span><span class="sxs-lookup"><span data-stu-id="d0f80-206">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
- [<span data-ttu-id="d0f80-207">XPathNavigator в преобразованиях</span><span class="sxs-lookup"><span data-stu-id="d0f80-207">XPathNavigator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)  
- [<span data-ttu-id="d0f80-208">XPathNodeIterator в преобразованиях</span><span class="sxs-lookup"><span data-stu-id="d0f80-208">XPathNodeIterator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)  
- [<span data-ttu-id="d0f80-209">Ввод XPathDocument в XslTransform</span><span class="sxs-lookup"><span data-stu-id="d0f80-209">XPathDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)  
- [<span data-ttu-id="d0f80-210">Ввод XmlDataDocument в XslTransform</span><span class="sxs-lookup"><span data-stu-id="d0f80-210">XmlDataDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)  
- [<span data-ttu-id="d0f80-211">Ввод XmlDocument в XslTransform</span><span class="sxs-lookup"><span data-stu-id="d0f80-211">XmlDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)
