---
title: "Область действия пространств имен по умолчанию в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: d4cce80c-342f-4097-be8b-40ab0bfa90ba
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 138115cb1a5ec2e2c513419a32a9ebaec9c90d61
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017


---
# <a name="scope-of-default-namespaces-in-visual-basic"></a><span data-ttu-id="ec823-102">Область действия пространств имен по умолчанию в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ec823-102">Scope of Default Namespaces in Visual Basic</span></span>
<span data-ttu-id="ec823-103">Применяемые по умолчанию пространства имен, представленные в XML-дереве, находятся вне области запросов.</span><span class="sxs-lookup"><span data-stu-id="ec823-103">Default namespaces as represented in the XML tree are not in scope for queries.</span></span> <span data-ttu-id="ec823-104">Если имеется XML, который находится в пространстве имен по умолчанию, то необходимо объявить <xref:System.Xml.Linq.XNamespace>переменной и использовать ее в сочетании с локальным именем для получения полного имени для использования в запросе.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="ec823-104">If you have XML that is in a default namespace, you still must declare an <xref:System.Xml.Linq.XNamespace> variable, and combine it with the local name to make a qualified name to be used in the query.</span></span>  
  
 <span data-ttu-id="ec823-105">Одной из наиболее типичных проблем при запросах к XML-деревьям является то, что, если XML-дерево содержит пространство имен по умолчанию, разработчик иногда пишет запрос так, как если бы XML-код не располагался в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="ec823-105">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="ec823-106">Первый набор примеров в данном разделе показывает типичный способ загрузки XML в пространстве имен по умолчанию и неправильного запроса к нему.</span><span class="sxs-lookup"><span data-stu-id="ec823-106">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, but is queried improperly.</span></span>  
  
 <span data-ttu-id="ec823-107">Второй набор примеров показывает необходимые исправления для запроса XML в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="ec823-107">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec823-108">Пример</span><span class="sxs-lookup"><span data-stu-id="ec823-108">Example</span></span>  
 <span data-ttu-id="ec823-109">Этот пример показывает создание XML в пространстве имен, а также запрос, возвращающий пустой результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="ec823-109">This example shows the creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ec823-110">Код</span><span class="sxs-lookup"><span data-stu-id="ec823-110">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="ec823-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ec823-111">Comments</span></span>  
 <span data-ttu-id="ec823-112">Этот пример выдает следующий результат:</span><span class="sxs-lookup"><span data-stu-id="ec823-112">This example produces the following result:</span></span>  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="ec823-113">Пример</span><span class="sxs-lookup"><span data-stu-id="ec823-113">Example</span></span>  
 <span data-ttu-id="ec823-114">Этот пример показывает создание XML в пространстве имен, а также запрос, код которого написан правильно.</span><span class="sxs-lookup"><span data-stu-id="ec823-114">This example shows the creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="ec823-115">В отличие от вышеприведенного примера неправильным кодом правильный подход с использованием Visual Basic заключается в объявлении и инициализации глобального пространства имен.</span><span class="sxs-lookup"><span data-stu-id="ec823-115">In contrast to the incorrectly coded example above, the correct approach when using Visual Basic is to declare and initialize a global default namespace.</span></span> <span data-ttu-id="ec823-116">При этом все свойства XML помещаются в пространство имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ec823-116">This places all XML properties in the default namespace.</span></span> <span data-ttu-id="ec823-117">Для последующей правильной работы примера не требуется больше никаких изменений.</span><span class="sxs-lookup"><span data-stu-id="ec823-117">No other modifications are required to the example to make it work properly.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ec823-118">Код</span><span class="sxs-lookup"><span data-stu-id="ec823-118">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="ec823-119">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ec823-119">Comments</span></span>  
 <span data-ttu-id="ec823-120">Этот пример выдает следующий результат:</span><span class="sxs-lookup"><span data-stu-id="ec823-120">This example produces the following result:</span></span>  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="ec823-121">См. также</span><span class="sxs-lookup"><span data-stu-id="ec823-121">See Also</span></span>  
 [<span data-ttu-id="ec823-122">Работа с пространствами имен XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec823-122">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
