---
title: Как создать документ с пространствами имен (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: cc5b0d4d-360c-4ada-94fa-2d2916e989be
ms.openlocfilehash: bbd23840b0356cf14d2c7d6cb71591fe6461a8bd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332582"
---
# <a name="how-to-create-a-document-with-namespaces-linq-to-xml-visual-basic"></a>Практическое руководство. Создание документа с пространствами имен (LINQ to XML) (Visual Basic)
В этом разделе описано, как создать документ с пространствами имен в Visual Basic.  
  
 При использовании литералов XML в Visual Basic пользователи могут задавать одно глобальное пространство имен XML. Это пространство имен является пространством имен по умолчанию как для литералов, так и для свойств XML. Пространство имен XML по умолчанию можно задать как на уровне проекта, так и на уровне файла. Если оно задается на уровне файла, то оно переопределяет пространство имен по умолчанию, заданное на уровне проекта.  
  
 Можно также задавать другие пространства имен и указывать префиксы для них.  
  
 Как пространства имен по умолчанию, так и пространства имен с префиксами можно задавать при помощи ключа `Imports`.  
  
 Дополнительные сведения см. [в разделе Введение в XML-литералы в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-xml-literals.md).  
  
 Обратите внимание, что пространство имен XML по умолчанию применимо только к элементам, а не к атрибутам. Атрибуты по умолчанию никогда не находятся в пространстве имен. Однако можно использовать префикс пространства имен, чтобы ввести атрибут в пространство имен.  
  
## <a name="example"></a>Пример  
 В этом примере создается документ, который содержит пространство имен.  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child aw:Att="attvalue"/>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child aw:Att="attvalue" />  
</aw:Root>  
```  
  
## <a name="example"></a>Пример  
 В этом примере создается документ, который содержит два пространства имен, каждое из которых является пространством имен по умолчанию.  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child Att="attvalue"/>  
                <fc:Child2>child2 content</fc:Child2>  
            </Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Root xmlns:fc="www.fourthcoffee.com" xmlns="http://www.adventure-works.com">  
  <Child Att="attvalue" />  
  <fc:Child2>child2 content</fc:Child2>  
</Root>  
```  
  
## <a name="example"></a>Пример  
 В этом примере создается документ, который содержит несколько пространств имен с префиксами.  
  
 При сериализации XML-дерева [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] создает декларации пространства имен таким образом, чтобы каждый элемент находился в верном пространстве имен.  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <fc:Child>  
                    <aw:DifferentChild>other content</aw:DifferentChild>  
                </fc:Child>  
                <aw:Child2>c2 content</aw:Child2>  
                <fc:Child3>c3 content</fc:Child3>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a>См. также

- [Общие сведения о пространствах имен (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)
