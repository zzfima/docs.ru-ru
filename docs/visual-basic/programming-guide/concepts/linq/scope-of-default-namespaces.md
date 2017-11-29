---
title: "Область действия пространств имен по умолчанию в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4cce80c-342f-4097-be8b-40ab0bfa90ba
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3aaf5395f1216b0cb56f2d1f003e42ed30790012
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="scope-of-default-namespaces-in-visual-basic"></a><span data-ttu-id="58ed2-102">Область действия пространств имен по умолчанию в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="58ed2-102">Scope of Default Namespaces in Visual Basic</span></span>
<span data-ttu-id="58ed2-103">Применяемые по умолчанию пространства имен, представленные в XML-дереве, находятся вне области запросов.</span><span class="sxs-lookup"><span data-stu-id="58ed2-103">Default namespaces as represented in the XML tree are not in scope for queries.</span></span> <span data-ttu-id="58ed2-104">Если имеется XML, расположенный в используемом по умолчанию пространстве имен, для получения полного имени, которое может быть применено в запросе, то необходимо объявить переменную <xref:System.Xml.Linq.XNamespace> и использовать ее в сочетании с локальным именем.</span><span class="sxs-lookup"><span data-stu-id="58ed2-104">If you have XML that is in a default namespace, you still must declare an <xref:System.Xml.Linq.XNamespace> variable, and combine it with the local name to make a qualified name to be used in the query.</span></span>  
  
 <span data-ttu-id="58ed2-105">Одной из наиболее типичных проблем при запросах к XML-деревьям является то, что, если XML-дерево содержит пространство имен по умолчанию, разработчик иногда пишет запрос так, как если бы XML-код не располагался в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="58ed2-105">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="58ed2-106">Первый набор примеров в данном разделе показывает типичный способ загрузки XML в пространстве имен по умолчанию и неправильного запроса к нему.</span><span class="sxs-lookup"><span data-stu-id="58ed2-106">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, but is queried improperly.</span></span>  
  
 <span data-ttu-id="58ed2-107">Второй набор примеров показывает необходимые исправления для запроса XML в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="58ed2-107">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58ed2-108">Пример</span><span class="sxs-lookup"><span data-stu-id="58ed2-108">Example</span></span>  
 <span data-ttu-id="58ed2-109">Этот пример показывает создание XML в пространстве имен, а также запрос, возвращающий пустой результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="58ed2-109">This example shows the creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
### <a name="code"></a><span data-ttu-id="58ed2-110">Код</span><span class="sxs-lookup"><span data-stu-id="58ed2-110">Code</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root xmlns='http://www.adventure-works.com'>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
                From el In root.<Child> _  
                Select el  
        Console.WriteLine("Result set follows:")  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="58ed2-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="58ed2-111">Comments</span></span>  
 <span data-ttu-id="58ed2-112">Этот пример выдает следующий результат:</span><span class="sxs-lookup"><span data-stu-id="58ed2-112">This example produces the following result:</span></span>  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="58ed2-113">Пример</span><span class="sxs-lookup"><span data-stu-id="58ed2-113">Example</span></span>  
 <span data-ttu-id="58ed2-114">Этот пример показывает создание XML в пространстве имен, а также запрос, код которого написан правильно.</span><span class="sxs-lookup"><span data-stu-id="58ed2-114">This example shows the creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="58ed2-115">В отличие от вышеприведенного примера неправильным кодом правильный подход с использованием Visual Basic заключается в объявлении и инициализации глобального пространства имен.</span><span class="sxs-lookup"><span data-stu-id="58ed2-115">In contrast to the incorrectly coded example above, the correct approach when using Visual Basic is to declare and initialize a global default namespace.</span></span> <span data-ttu-id="58ed2-116">При этом все свойства XML помещаются в пространство имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="58ed2-116">This places all XML properties in the default namespace.</span></span> <span data-ttu-id="58ed2-117">Для последующей правильной работы примера не требуется больше никаких изменений.</span><span class="sxs-lookup"><span data-stu-id="58ed2-117">No other modifications are required to the example to make it work properly.</span></span>  
  
### <a name="code"></a><span data-ttu-id="58ed2-118">Код</span><span class="sxs-lookup"><span data-stu-id="58ed2-118">Code</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root xmlns='http://www.adventure-works.com'>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
                From el In root.<Child> _  
                Select el  
        Console.WriteLine("Result set follows:")  
        For Each el As XElement In c1  
            Console.WriteLine(el.Value)  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="58ed2-119">Комментарии</span><span class="sxs-lookup"><span data-stu-id="58ed2-119">Comments</span></span>  
 <span data-ttu-id="58ed2-120">Этот пример выдает следующий результат:</span><span class="sxs-lookup"><span data-stu-id="58ed2-120">This example produces the following result:</span></span>  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="58ed2-121">См. также</span><span class="sxs-lookup"><span data-stu-id="58ed2-121">See Also</span></span>  
 [<span data-ttu-id="58ed2-122">Работа с пространствами имен XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="58ed2-122">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
