---
title: Объекты расширения XSLT
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a4ebdbad-087c-4cfe-acc0-17c48142f81a
caps.latest.revision: 3
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 72b1605c6bc5a0f3cbc4417d043ab21bf0bb787e
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="xslt-extension-objects"></a><span data-ttu-id="07d7f-102">Объекты расширения XSLT</span><span class="sxs-lookup"><span data-stu-id="07d7f-102">XSLT Extension Objects</span></span>
<span data-ttu-id="07d7f-103">Объекты расширения используются для расширения функциональности таблиц стилей.</span><span class="sxs-lookup"><span data-stu-id="07d7f-103">Extension objects are used to extend the functionality of style sheets.</span></span> <span data-ttu-id="07d7f-104">Объекты расширения обслуживаются классом <xref:System.Xml.Xsl.XsltArgumentList>.</span><span class="sxs-lookup"><span data-stu-id="07d7f-104">Extension objects are maintained by the <xref:System.Xml.Xsl.XsltArgumentList> class.</span></span>  
  
 <span data-ttu-id="07d7f-105">Далее приведены преимущества использования объекта расширения в сравнении с внедренными скриптами.</span><span class="sxs-lookup"><span data-stu-id="07d7f-105">The following are advantages to using an extension object rather than embedded script:</span></span>  
  
-   <span data-ttu-id="07d7f-106">Обеспечивает улучшенную инкапсуляцию и повторное использование классов.</span><span class="sxs-lookup"><span data-stu-id="07d7f-106">Provides better encapsulation and reuse of classes.</span></span>  
  
-   <span data-ttu-id="07d7f-107">Уменьшает размер и улучшает обслуживание таблиц стилей.</span><span class="sxs-lookup"><span data-stu-id="07d7f-107">Allows style sheets to be smaller and more maintainable.</span></span>  
  
 <span data-ttu-id="07d7f-108">Объекты расширения XSLT добавляются в объект <xref:System.Xml.Xsl.XsltArgumentList> с помощью метода <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="07d7f-108">XSLT extension objects are added to the <xref:System.Xml.Xsl.XsltArgumentList> object using the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="07d7f-109">В это время с объектом расширения связываются полное имя и URI-код пространства имен.</span><span class="sxs-lookup"><span data-stu-id="07d7f-109">A qualified name and namespace URI are associated with the extension object at that time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07d7f-110">Чтобы вызвать метод <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>, необходим набор разрешений FullTrust.</span><span class="sxs-lookup"><span data-stu-id="07d7f-110">The FullTrust permission set is required to call the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="07d7f-111">См. дополнительные сведения о [защите доступа к коду](http://msdn.microsoft.com/library/23a20143-241d-4fe5-9d9f-3933fd594c03) и [именованных наборов разрешений (NIB)](https://msdn.microsoft.com/library/08250d67-c99d-4ab0-8d2b-b0e12019f6e3).</span><span class="sxs-lookup"><span data-stu-id="07d7f-111">For more information, see [Code Access Security](http://msdn.microsoft.com/library/23a20143-241d-4fe5-9d9f-3933fd594c03) and [NIB: Named Permission Sets](https://msdn.microsoft.com/library/08250d67-c99d-4ab0-8d2b-b0e12019f6e3).</span></span>  
  
 <span data-ttu-id="07d7f-112">Объекты расширения возвращают один из четырех базовых типов данных XPath: `number`, `string`, `Boolean` и `node set`.</span><span class="sxs-lookup"><span data-stu-id="07d7f-112">The data types returned from extension objects are one of the four basic XPath data types of `number`, `string`, `Boolean`, and `node set`.</span></span>  
  
 <span data-ttu-id="07d7f-113">Любой метод, который определен с ключевым словом `params`, позволяющим передавать точно не установленное количество параметров, в настоящее время не поддерживается классом <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="07d7f-113">Any method that is defined with the `params` keyword, which allows an unspecified number of parameters to be passed, is not currently supported by the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="07d7f-114">Таблицы стилей XSLT, которые используют любой метод, определенный с ключевым словом `params`, не будут работать правильно.</span><span class="sxs-lookup"><span data-stu-id="07d7f-114">XSLT style sheets that utilize any method defined with the `params` keyword will not work correctly.</span></span> <span data-ttu-id="07d7f-115">Дополнительные сведения см. в руководстве по [params](~/docs/csharp/language-reference/keywords/params.md).</span><span class="sxs-lookup"><span data-stu-id="07d7f-115">For details, see [params](~/docs/csharp/language-reference/keywords/params.md).</span></span>  
  
### <a name="to-use-an-xslt-extension-object"></a><span data-ttu-id="07d7f-116">Использование объекта расширения XSLT</span><span class="sxs-lookup"><span data-stu-id="07d7f-116">To use an XSLT extension object</span></span>  
  
1.  <span data-ttu-id="07d7f-117">Создайте объект <xref:System.Xml.Xsl.XsltArgumentList> и добавьте объект расширения с помощью метода <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="07d7f-117">Create an <xref:System.Xml.Xsl.XsltArgumentList> object and add the extension object using <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span>  
  
2.  <span data-ttu-id="07d7f-118">Вызовите объект расширения из таблицы стилей.</span><span class="sxs-lookup"><span data-stu-id="07d7f-118">Call the extension object from the style sheet.</span></span>  
  
3.  <span data-ttu-id="07d7f-119">Передайте объект <xref:System.Xml.Xsl.XsltArgumentList> методу <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="07d7f-119">Pass the <xref:System.Xml.Xsl.XsltArgumentList> object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07d7f-120">См. также</span><span class="sxs-lookup"><span data-stu-id="07d7f-120">See Also</span></span>  
 [<span data-ttu-id="07d7f-121">Преобразования XSLT</span><span class="sxs-lookup"><span data-stu-id="07d7f-121">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)  
 [<span data-ttu-id="07d7f-122">Рекомендации по безопасности XSLT</span><span class="sxs-lookup"><span data-stu-id="07d7f-122">XSLT Security Considerations</span></span>](../../../../docs/standard/data/xml/xslt-security-considerations.md)
