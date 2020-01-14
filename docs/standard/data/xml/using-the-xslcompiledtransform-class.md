---
title: Использование класса XslCompiledTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
ms.openlocfilehash: 6fc29b523e59590138cb7ca4db1b0da1bfee99c8
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937933"
---
# <a name="using-the-xslcompiledtransform-class"></a><span data-ttu-id="054b2-102">Использование класса XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="054b2-102">Using the XslCompiledTransform Class</span></span>
<span data-ttu-id="054b2-103">Класс <xref:System.Xml.Xsl.XslCompiledTransform> является обработчиком XSLT в платформе Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="054b2-103">The <xref:System.Xml.Xsl.XslCompiledTransform> class is the Microsoft .NET Framework XSLT processor.</span></span> <span data-ttu-id="054b2-104">Этот класс используется для компиляции таблиц стилей и выполнения преобразований XSLT.</span><span class="sxs-lookup"><span data-stu-id="054b2-104">This class is used to compile style sheets and execute XSLT transformations.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="054b2-105">Хотя класс <xref:System.Xml.Xsl.XslCompiledTransform> имеет более высокий общий уровень производительности, чем класс <xref:System.Xml.Xsl.XslTransform>, метод <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> класса <xref:System.Xml.Xsl.XslCompiledTransform> может выполняться медленнее, чем метод <xref:System.Xml.Xsl.XslTransform.Load%2A> класса <xref:System.Xml.Xsl.XslTransform> при первом вызове преобразования.</span><span class="sxs-lookup"><span data-stu-id="054b2-105">Although the overall performance of the <xref:System.Xml.Xsl.XslCompiledTransform> class is better than the <xref:System.Xml.Xsl.XslTransform> class, the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslCompiledTransform> class might perform more slowly than the <xref:System.Xml.Xsl.XslTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslTransform> class the first time it is called on a transformation.</span></span> <span data-ttu-id="054b2-106">Причина этого заключается в необходимости компиляции XSLT-файла перед его загрузкой.</span><span class="sxs-lookup"><span data-stu-id="054b2-106">This is because the XSLT file must be compiled before it is loaded.</span></span> <span data-ttu-id="054b2-107">См. дополнительные сведения о [сравнении XslCompiledTransform и XslTransform](https://docs.microsoft.com/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform)</span><span class="sxs-lookup"><span data-stu-id="054b2-107">For more information, see the following blog post: [XslCompiledTransform Slower than XslTransform?](https://docs.microsoft.com/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="054b2-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="054b2-108">In This Section</span></span>  
 [<span data-ttu-id="054b2-109">Входные данные для класса XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="054b2-109">Inputs to the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/inputs-to-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="054b2-110">Описываются доступные входные параметры XSLT.</span><span class="sxs-lookup"><span data-stu-id="054b2-110">Describes the available XSLT input options.</span></span>  
  
 [<span data-ttu-id="054b2-111">Параметры вывода в классе XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="054b2-111">Output Options on the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/output-options-on-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="054b2-112">Описываются доступные выходные параметры XSLT.</span><span class="sxs-lookup"><span data-stu-id="054b2-112">Describes the available XSLT output options.</span></span>  
  
 [<span data-ttu-id="054b2-113">Разрешение внешних ресурсов в ходе обработки XSLT</span><span class="sxs-lookup"><span data-stu-id="054b2-113">Resolving External Resources During XSLT Processing</span></span>](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md)  
 <span data-ttu-id="054b2-114">Обсуждается использование класса <xref:System.Xml.XmlResolver> для разрешения внешних ресурсов.</span><span class="sxs-lookup"><span data-stu-id="054b2-114">Discusses using the <xref:System.Xml.XmlResolver> class to resolve external resources.</span></span>  
  
 [<span data-ttu-id="054b2-115">Расширение таблиц стилей XSLT</span><span class="sxs-lookup"><span data-stu-id="054b2-115">Extending XSLT Style Sheets</span></span>](../../../../docs/standard/data/xml/extending-xslt-style-sheets.md)  
 <span data-ttu-id="054b2-116">Обсуждается поддержка расширений XSLT.</span><span class="sxs-lookup"><span data-stu-id="054b2-116">Discusses how XSLT extensions are supported.</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="054b2-117">Устранимые ошибки XSLT</span><span class="sxs-lookup"><span data-stu-id="054b2-117">Recoverable XSLT Errors</span></span>](../../../../docs/standard/data/xml/recoverable-xslt-errors.md)|<span data-ttu-id="054b2-118">Содержит список поведений по выбору, допустимых в соответствии с рекомендациями консорциума W3C по XSLT 1.0, и описывает, каким образом эти поведения обрабатываются классом <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="054b2-118">Lists discretionary behaviors allowed by the World Wide Web Consortium (W3C) XSLT 1.0 recommendation and describes how these behaviors are handled by the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>|  
|[<span data-ttu-id="054b2-119">Как преобразовать фрагмент узла</span><span class="sxs-lookup"><span data-stu-id="054b2-119">How to: Transform a Node Fragment</span></span>](../../../../docs/standard/data/xml/how-to-transform-a-node-fragment.md)|<span data-ttu-id="054b2-120">Описывает процесс преобразования фрагмента узла.</span><span class="sxs-lookup"><span data-stu-id="054b2-120">Describes how to transform a node fragment.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="054b2-121">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="054b2-121">Related Sections</span></span>  
 [<span data-ttu-id="054b2-122">Миграция с класса XslTransform</span><span class="sxs-lookup"><span data-stu-id="054b2-122">Migrating From the XslTransform Class</span></span>](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 <span data-ttu-id="054b2-123">Обсуждается перенос кода из класса <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="054b2-123">Discusses how to migrate code from the <xref:System.Xml.Xsl.XslTransform> class</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="054b2-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="054b2-124">See also</span></span>

- <xref:System.Xml.Xsl.XsltSettings>
- <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>
