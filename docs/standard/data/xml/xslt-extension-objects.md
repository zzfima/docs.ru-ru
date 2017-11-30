---
title: "Объекты расширения XSLT"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4ebdbad-087c-4cfe-acc0-17c48142f81a
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2916f7da6b990cddef9b86559a71b5206351d558
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xslt-extension-objects"></a><span data-ttu-id="23c7d-102">Объекты расширения XSLT</span><span class="sxs-lookup"><span data-stu-id="23c7d-102">XSLT Extension Objects</span></span>
<span data-ttu-id="23c7d-103">Объекты расширения используются для расширения функциональности таблиц стилей.</span><span class="sxs-lookup"><span data-stu-id="23c7d-103">Extension objects are used to extend the functionality of style sheets.</span></span> <span data-ttu-id="23c7d-104">Объекты расширения обслуживаются классом <xref:System.Xml.Xsl.XsltArgumentList>.</span><span class="sxs-lookup"><span data-stu-id="23c7d-104">Extension objects are maintained by the <xref:System.Xml.Xsl.XsltArgumentList> class.</span></span>  
  
 <span data-ttu-id="23c7d-105">Далее приведены преимущества использования объекта расширения в сравнении с внедренными скриптами.</span><span class="sxs-lookup"><span data-stu-id="23c7d-105">The following are advantages to using an extension object rather than embedded script:</span></span>  
  
-   <span data-ttu-id="23c7d-106">Обеспечивает улучшенную инкапсуляцию и повторное использование классов.</span><span class="sxs-lookup"><span data-stu-id="23c7d-106">Provides better encapsulation and reuse of classes.</span></span>  
  
-   <span data-ttu-id="23c7d-107">Уменьшает размер и улучшает обслуживание таблиц стилей.</span><span class="sxs-lookup"><span data-stu-id="23c7d-107">Allows style sheets to be smaller and more maintainable.</span></span>  
  
 <span data-ttu-id="23c7d-108">Объекты расширения XSLT добавляются в объект <xref:System.Xml.Xsl.XsltArgumentList> с помощью метода <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="23c7d-108">XSLT extension objects are added to the <xref:System.Xml.Xsl.XsltArgumentList> object using the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="23c7d-109">В это время с объектом расширения связываются полное имя и URI-код пространства имен.</span><span class="sxs-lookup"><span data-stu-id="23c7d-109">A qualified name and namespace URI are associated with the extension object at that time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23c7d-110">Чтобы вызвать метод <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>, необходим набор разрешений FullTrust.</span><span class="sxs-lookup"><span data-stu-id="23c7d-110">The FullTrust permission set is required to call the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="23c7d-111">Дополнительные сведения см. в разделе [управления доступом для кода](http://msdn.microsoft.com/en-us/23a20143-241d-4fe5-9d9f-3933fd594c03) и [NIB: именованный набор разрешений](http://msdn.microsoft.com/en-us/08250d67-c99d-4ab0-8d2b-b0e12019f6e3).</span><span class="sxs-lookup"><span data-stu-id="23c7d-111">For more information, see [Code Access Security](http://msdn.microsoft.com/en-us/23a20143-241d-4fe5-9d9f-3933fd594c03) and [NIB: Named Permission Sets](http://msdn.microsoft.com/en-us/08250d67-c99d-4ab0-8d2b-b0e12019f6e3).</span></span>  
  
 <span data-ttu-id="23c7d-112">Объекты расширения возвращают один из четырех базовых типов данных XPath: `number`, `string`, `Boolean` и `node set`.</span><span class="sxs-lookup"><span data-stu-id="23c7d-112">The data types returned from extension objects are one of the four basic XPath data types of `number`, `string`, `Boolean`, and `node set`.</span></span>  
  
 <span data-ttu-id="23c7d-113">Любой метод, который определен с ключевым словом `params`, позволяющим передавать точно не установленное количество параметров, в настоящее время не поддерживается классом <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="23c7d-113">Any method that is defined with the `params` keyword, which allows an unspecified number of parameters to be passed, is not currently supported by the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="23c7d-114">Таблицы стилей XSLT, которые используют любой метод, определенный с ключевым словом `params`, не будут работать правильно.</span><span class="sxs-lookup"><span data-stu-id="23c7d-114">XSLT style sheets that utilize any method defined with the `params` keyword will not work correctly.</span></span> <span data-ttu-id="23c7d-115">Дополнительные сведения см. в разделе [params](~/docs/csharp/language-reference/keywords/params.md).</span><span class="sxs-lookup"><span data-stu-id="23c7d-115">For details, see [params](~/docs/csharp/language-reference/keywords/params.md).</span></span>  
  
### <a name="to-use-an-xslt-extension-object"></a><span data-ttu-id="23c7d-116">Использование объекта расширения XSLT</span><span class="sxs-lookup"><span data-stu-id="23c7d-116">To use an XSLT extension object</span></span>  
  
1.  <span data-ttu-id="23c7d-117">Создайте объект <xref:System.Xml.Xsl.XsltArgumentList> и добавьте объект расширения с помощью метода <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="23c7d-117">Create an <xref:System.Xml.Xsl.XsltArgumentList> object and add the extension object using <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span>  
  
2.  <span data-ttu-id="23c7d-118">Вызовите объект расширения из таблицы стилей.</span><span class="sxs-lookup"><span data-stu-id="23c7d-118">Call the extension object from the style sheet.</span></span>  
  
3.  <span data-ttu-id="23c7d-119">Передайте объект <xref:System.Xml.Xsl.XsltArgumentList> методу <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="23c7d-119">Pass the <xref:System.Xml.Xsl.XsltArgumentList> object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23c7d-120">См. также</span><span class="sxs-lookup"><span data-stu-id="23c7d-120">See Also</span></span>  
 [<span data-ttu-id="23c7d-121">Преобразования XSLT</span><span class="sxs-lookup"><span data-stu-id="23c7d-121">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)  
 [<span data-ttu-id="23c7d-122">Рекомендации по безопасности XSLT</span><span class="sxs-lookup"><span data-stu-id="23c7d-122">XSLT Security Considerations</span></span>](../../../../docs/standard/data/xml/xslt-security-considerations.md)
