---
title: Работа с глобальными пространствами имен (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 0a8064d5-e02f-4315-ad48-6deaa443a2f0
ms.openlocfilehash: 80510e370e0a9c7ab27cb5177d9b547ead82715c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350992"
---
# <a name="working-with-global-namespaces-visual-basic-linq-to-xml"></a>Работа с глобальными пространствами имен (Visual Basic) (LINQ to XML)
Одной из основных функций литералов XML в Visual Basic является возможность объявлять пространства имен XML с помощью инструкции `Imports`. Используя эту возможность, можно объявить либо пространство имен XML, использующее префикс, либо пространство имен XML по умолчанию.  
  
 Данная возможность полезна в двух ситуациях. Во-первых, пространства имен, объявленные в XML-литералах, не переносятся во внедренные выражения. Применение деклараций глобальных пространств имен способствует снижению объема работы, которую необходимо выполнить в целях использования внедренных выражений с пространствами имен. Во-вторых, необходимо объявить глобальные пространства имен в целях использования пространств имен с XML-свойствами.  
  
 Глобальные пространства имен можно объявлять на уровне проекта. Глобальные пространства имен можно также объявить на уровне модуля, что приводит к переопределению глобальных пространств имен уровня проекта. Наконец, можно переопределить глобальные пространства имен в XML-литерале.  
  
 При использовании XML-литералов или XML-свойств, находящихся в пространствах имен, объявленных глобально, можно видеть развернутое имя XML-литералов или свойств при наведении на них курсора в Visual Studio. Развернутое имя отобразится в подсказке.  
  
 С помощью метода <xref:System.Xml.Linq.XNamespace> можно вызвать объект `GetXmlNamespace`, соответствующий глобальному пространству имен.  
  
## <a name="examples-of-global-namespaces"></a>Примеры глобальных пространств имен  
 В следующем примере объявляется глобальное пространство имен по умолчанию с помощью инструкции `Imports`, а затем используется XML-литерал для инициализации объекта <xref:System.Xml.Linq.XElement> в данном пространстве имен:  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <Root/>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Root xmlns="http://www.adventure-works.com" />  
```  
  
 В следующем примере объявляется глобальное пространство имен с префиксом, а затем используется XML-литерал для инициализации элемента:  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root/>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" />  
```  
  
## <a name="global-namespaces-and-embedded-expressions"></a>Глобальные пространства имен и внедренные выражения  
 Пространства имен, объявленные в XML-литералах, не переносятся во внедренные выражения. В следующем примере объявляется пространство имен по умолчанию. Затем в нем используется внедренное выражение для элемента `Child`.  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <%= <Child/> %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child xmlns="" />  
</Root>  
```  
  
 Очевидно, что результирующий XML включает декларацию пространства имен по умолчанию, так что элемент `Child` находится вне пространства имен.  
  
 Можно повторно объявить пространство имен во внедренном выражении следующим образом:  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <%= <Child xmlns="http://www.adventure-works.com"/> %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child xmlns="http://www.adventure-works.com" />  
</Root>  
```  
  
 Однако это более сложный и менее выгодный способ по сравнению с использованием глобального пространства имен по умолчанию. При наличии глобального пространства имен по умолчанию при использовании XML-литералов можно не декларировать пространства имен. Результирующий XML будет находиться в пространстве имен, объявленном глобально.  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <Root>  
                                   <%= <Child/> %>  
                               </Root>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child />  
</Root>  
```  
  
## <a name="using-namespaces-with-xml-properties"></a>Использование пространств имен с XML-свойствами  
 При работе с XML-деревом, находящимся в пространстве имен, и использовании XML-свойств необходимо использовать глобальное пространство имен, чтобы XML-свойства также находились в правильно заданном пространстве имен. В следующем примере объявляется XML-дерево в пространстве имен. Затем в нем происходит вывод на печать числа элементов `Child`.  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <Child>content</Child>  
    </Root>  
Console.WriteLine(root.<Child>.Count())  
```  
  
 Данный пример указывает на отсутствие элементов `Child`. Выводятся следующие результаты:  
  
```console  
0  
```  
  
 Однако после объявления глобального пространства имен по умолчанию в нем будут находиться и XML-литерал и XML-свойство.  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child>content</Child>  
            </Root>  
        Console.WriteLine(root.<Child>.Count())  
    End Sub  
End Module  
```  
  
 Данный пример указывает на отсутствие одного элемента `Child`. Выводятся следующие результаты:  
  
```console  
1  
```  
  
 После объявления глобального пространства имен с префиксом можно использовать префикс как для XML-литералов, так и для XML-свойств.  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child>content</aw:Child>  
            </aw:Root>  
        Console.WriteLine(root.<aw:Child>.Count())  
    End Sub  
End Module  
```  
  
## <a name="xnamespace-and-global-namespaces"></a>XNamespace и глобальные пространства имен  
 Объект <xref:System.Xml.Linq.XNamespace> можно получить с помощью метода `GetXmlNamespace`:  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root/>  
        Dim xn As XNamespace = GetXmlNamespace(aw)  
        Console.WriteLine(xn)  
    End Sub  
End Module  
```  
  
 В этом примере выводятся следующие данные:  
  
```console  
http://www.adventure-works.com  
```  
  
## <a name="see-also"></a>См. также:

- [Общие сведения о пространствах имен (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)
