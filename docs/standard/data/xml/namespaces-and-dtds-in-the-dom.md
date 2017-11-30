---
title: "Пространства имен и DTD в DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e9b55c4-76ad-4f54-8d96-7ce4b4cf1e05
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 87a03883622ba63a8d999907305356905b36bf1c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="namespaces-and-dtds-in-the-dom"></a><span data-ttu-id="2264c-102">Пространства имен и DTD в DOM</span><span class="sxs-lookup"><span data-stu-id="2264c-102">Namespaces and DTDs in the DOM</span></span>
<span data-ttu-id="2264c-103">Определения типа документа (DTD) усложняют поддержку пространства имен.</span><span class="sxs-lookup"><span data-stu-id="2264c-103">Document type definitions (DTDs) complicate namespace support.</span></span> <span data-ttu-id="2264c-104">Например, приведенный ниже XML-файл содержит атрибуты по умолчанию с двоеточиями в имени.</span><span class="sxs-lookup"><span data-stu-id="2264c-104">For example, the following XML contains default attributes containing colons in their names.</span></span>  
  
```xml  
<!ATTLIST item x:id CDATA #IMPLIED>  
```  
  
 <span data-ttu-id="2264c-105">Ниже приведены возможные разрешения, если эта конструкция допустима:</span><span class="sxs-lookup"><span data-stu-id="2264c-105">The following are possible resolutions if this construct is allowed:</span></span>  
  
-   <span data-ttu-id="2264c-106">`x:` рассматривается как префикс пространства имен, но этот префикс должен быть разрешаемым с использованием декларации пространства имен `xmlns:x`, которое также должно быть в DTD.</span><span class="sxs-lookup"><span data-stu-id="2264c-106">The `x:` is treated as a namespace prefix, but this prefix must be resolvable using an `xmlns:x` namespace declaration, which must also exist somewhere in the DTD.</span></span> <span data-ttu-id="2264c-107">Сопоставлять этот префикс с чем-то иным в экземпляре документа - ошибка.</span><span class="sxs-lookup"><span data-stu-id="2264c-107">It is an error to map this prefix to something different in the instance document.</span></span>  
  
-   <span data-ttu-id="2264c-108">`x:` рассматривается как префикс пространства имен, но этот префикс всегда разрешается в контексте элементов экземпляра.</span><span class="sxs-lookup"><span data-stu-id="2264c-108">The `x:` is treated as a namespace prefix, but this prefix is always resolved in the context of the instance elements.</span></span> <span data-ttu-id="2264c-109">Это значит, что префикс может быть сопоставлен с другими URI пространства имен в зависимости от диапазона пространства имен, в котором находится элемент `item`.</span><span class="sxs-lookup"><span data-stu-id="2264c-109">This means the prefix could actually map to different namespace Uniform Resource Identifiers (URIs), depending on the namespace scope in which the `item` element appears.</span></span> <span data-ttu-id="2264c-110">Это поведение более предсказуемо, чем разрешение, данное в предшествующем пункте, но имеет другие сложные последствия, поскольку требует материализованных атрибутов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2264c-110">This behavior is more predictable than the resolution given in the earlier bullet, but it has other complicated ramifications because it requires the default attributes be materialized.</span></span>  
  
-   <span data-ttu-id="2264c-111">Двоеточие не обрабатывается, так как оно находится в DTD, имя атрибута - `x:y`, нет префикса и нет URI-кода пространства имен.</span><span class="sxs-lookup"><span data-stu-id="2264c-111">The colon is ignored because it is in a DTD, and the name of the attribute is `x:y`, no prefix and no namespace URI.</span></span>  
  
-   <span data-ttu-id="2264c-112">Двоеточие в атрибуте по умолчанию вызывает исключение, указывающее, что двоеточия в имена внутри DTD не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="2264c-112">The colon in the default attribute throws an exception, saying that colons in names inside a DTD are not supported.</span></span> <span data-ttu-id="2264c-113">Это дает прогнозируемость поведения, но лишает возможности загружать многие из DTD, опубликованные консорциумом W3C.</span><span class="sxs-lookup"><span data-stu-id="2264c-113">This results in a predictable behavior, but means you cannot load many of the World Wide Web Consortium (W3C) published DTDs.</span></span>  
  
-   <span data-ttu-id="2264c-114">Когда пользователь запрашивает проверку DTD, поддержка пространства имен для всего документа отключается.</span><span class="sxs-lookup"><span data-stu-id="2264c-114">When the user requests DTD validation, namespace support for the entire document is turned off.</span></span> <span data-ttu-id="2264c-115">Это позволяет загружать DTD консорциума W3C и обеспечивает прогнозируемость работы.</span><span class="sxs-lookup"><span data-stu-id="2264c-115">This makes it possible to load W3C DTDs and results in a predictable behavior.</span></span>  
  
 <span data-ttu-id="2264c-116">XML-данные в Microsoft .NET Framework реализует второй вариант для максимальной совместимости со стандартом W3C.</span><span class="sxs-lookup"><span data-stu-id="2264c-116">The XML in the Microsoft .NET Framework implements the second option for maximum W3C compatibility.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2264c-117">См. также</span><span class="sxs-lookup"><span data-stu-id="2264c-117">See Also</span></span>  
 [<span data-ttu-id="2264c-118">Модель объектов XML-документов (DOM)</span><span class="sxs-lookup"><span data-stu-id="2264c-118">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
