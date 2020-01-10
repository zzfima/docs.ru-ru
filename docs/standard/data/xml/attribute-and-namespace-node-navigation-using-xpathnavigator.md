---
title: Навигация по узлам атрибутов и пространств имен с помощью XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 23975f88-e0af-4b88-93de-9e20e11880ad
ms.openlocfilehash: 6809a2a47a9ca25a16a9be75a0a8a8b03f98a21d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711159"
---
# <a name="attribute-and-namespace-node-navigation-using-xpathnavigator"></a>Навигация по узлам атрибутов и пространств имен с помощью XPathNavigator
Класс <xref:System.Xml.XPath.XPathNavigator> предоставляет два набора методов навигации. Методы первого набора, описанные в руководстве по [навигации в наборах узлов с помощью XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md), используются для навигации в *наборах узлов* в объекте <xref:System.Xml.XPath.XPathDocument> или <xref:System.Xml.XmlDocument>. Методы второго набора, рассматриваемые в этом разделе, используются для навигации в *узлах атрибутов и пространств имен* в объекте <xref:System.Xml.XPath.XPathDocument> или <xref:System.Xml.XmlDocument>.  
  
## <a name="attribute-node-navigation"></a>Навигация по узлам атрибутов  
 Атрибуты представляют собой свойства элементов. Они не являются дочерними объектами элементов. Это различие важно отметить, поскольку методы класса <xref:System.Xml.XPath.XPathNavigator> используются для перемещения по узлам с общим родителем, по узлам-родителям и по дочерним узлам.  
  
 Так, методы <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A> и <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A> не используются для перемещения с элемента на атрибут или между атрибутами. Вместо этого атрибуты имеют собственные методы навигации.  
  
 Ниже перечислены методы перемещения по атрибутам класса <xref:System.Xml.XPath.XPathNavigator>.  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToAttribute%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToFirstAttribute%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToNextAttribute%2A>  
  
 Если текущий узел является элементом, то можно с помощью свойства <xref:System.Xml.XPath.XPathNavigator.HasAttributes%2A> определить, существуют ли атрибуты, связанные с этим элементом. Если известно, что элемент имеет атрибуты, к этим атрибутам можно обратиться с помощью нескольких методов. Чтобы получить один атрибут из элемента, используйте метод <xref:System.Xml.XPath.XPathNavigator.GetAttribute%2A>. Для перемещения <xref:System.Xml.XPath.XPathNavigator> к определенному атрибуту используйте метод <xref:System.Xml.XPath.XPathNavigator.MoveToAttribute%2A>. Кроме того, можно осуществить перебор всех атрибутов элемента с помощью метода <xref:System.Xml.XPath.XPathNavigator.MoveToFirstAttribute%2A>, после чего выполняется несколько вызовов метода <xref:System.Xml.XPath.XPathNavigator.MoveToNextAttribute%2A>.  
  
> [!NOTE]
> При позиционировании объекта <xref:System.Xml.XPath.XPathNavigator> на узле атрибута или пространства имен методы <xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFollowing%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A> и <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A> всегда возвращают `false` и не влияют на позицию <xref:System.Xml.XPath.XPathNavigator>. Исключениями являются методы <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A> и <xref:System.Xml.XPath.XPathNavigator.MoveToRoot%2A>.  
  
## <a name="namespace-node-navigation"></a>Перемещение по узлам пространств имен  
 С каждым элементом связан набор узлов пространств имен, по одному на каждый уникальный префикс пространства имен, привязанный к URI-коду пространства имен в области для этого элемента (включая префикс XML, привязанный к пространству имен `http://www.w3.org/XML/1998/namespace`, который неявно объявляется в каждом XML-документе), а также один для пространства имен по умолчанию, если он находится в области для данного элемента. Элемент является родителем каждого из этих узлов пространства имен, однако узел пространства имен не является дочерним элементом своего родительского элемента.  
  
 Так же, как и в случае с атрибутами, методы <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A> и <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A> не используются для перемещения с элемента на узел пространства имен или между узлами пространств имен. Вместо этого узлы пространств имен имеют собственные методы навигации.  
  
 Ниже перечислены методы перемещения по пространствам имен класса <xref:System.Xml.XPath.XPathNavigator>.  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToNamespace%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A>  
  
 В XML-документе всегда имеется по меньшей мере один узел пространства имен в области для любого элемента. Это узел пространства имен с префиксом `xml` и URI-кодом пространства имен `http://www.w3.org/XML/1998/namespace`. Чтобы получить URI-код пространства имен в области с указанным префиксом, используйте метод <xref:System.Xml.XPath.XPathNavigator.GetNamespace%2A>. Для перемещения объекта <xref:System.Xml.XPath.XPathNavigator> к определенному узлу пространства имен используйте метод <xref:System.Xml.XPath.XPathNavigator.MoveToNamespace%2A>. Кроме того, можно осуществить перебор всех узлов пространств имен в области для элемента с помощью метода <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A>, после чего выполняется несколько вызовов метода <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A>.  
  
> [!NOTE]
> При позиционировании объекта <xref:System.Xml.XPath.XPathNavigator> на узле атрибута или пространства имен методы <xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFollowing%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A> и <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A> всегда возвращают `false` и не влияют на позицию <xref:System.Xml.XPath.XPathNavigator>. Исключениями являются методы <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A> и <xref:System.Xml.XPath.XPathNavigator.MoveToRoot%2A>.  
  
### <a name="the-xpathnamespacescope-enumeration"></a>Перечисление XPathNamespaceScope  
 При навигации по узлам пространств имен можно вызывать методы <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> и <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A> с параметром <xref:System.Xml.XPath.XPathNamespaceScope>. Эти методы функционируют иначе, чем в тех случаях, когда они вызываются без параметров. Перечисление <xref:System.Xml.XPath.XPathNamespaceScope> имеет значения <xref:System.Xml.XPath.XPathNamespaceScope.All>, <xref:System.Xml.XPath.XPathNamespaceScope.ExcludeXml> или <xref:System.Xml.XPath.XPathNamespaceScope.Local>.  
  
 Следующие примеры показывают, что пространства имен возвращаются с помощью методов <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> и <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A> в различных областях XML-документа.  
  
```xml  
<root>  
    <element1 xmlns="http://www.contoso.com" xmlns:books="http://www.contoso.com/books">  
        <element2 />  
    </element1>  
</root>  
```  
  
 Последовательность пространств имен (пространство имен, в котором располагается объект<xref:System.Xml.XPath.XPathNavigator> после вызова метода <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> и ряда вызовов метода <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A>) имеет следующий вид.  
  
- При позиционировании на `element2`: `xmlns:books="http://www.contoso.com/books"`, `xmlns="http://www.contoso.com"` и `xmlns:xml="http://www.w3.org/XML/1998/namespace"`.  
  
- При позиционировании на `element1`: `xmlns:books="http://www.contoso.com/books"`, `xmlns="http://www.contoso.com"` и `xmlns:xml="http://www.w3.org/XML/1998/namespace"`.  
  
- При позиционировании на `root`: `xmlns:xml="http://www.w3.org/XML/1998/namespace".`  
  
> [!NOTE]
> Класс <xref:System.Xml.XPath.XPathNavigator> возвращает узлы пространства имен в обратном порядке документа. Поэтому <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> существенно перемещается к последнему узлу пространства имен в текущей области видимости.  
  
 Следующие примеры показывают, что пространства имен возвращаются с помощью методов <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> и <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A> с использованием перечисления <xref:System.Xml.XPath.XPathNamespaceScope>, указанного в различных областях XML-документа.  
  
```xml  
<root xmlns="http://www.contoso.com" xmlns:a="http://www.contoso.com/a" xmlns:b="http://www.contoso.com/b">  
    <child1 xmlns="" xmlns:a="urn:a">  
        <child2 xmlns:c="urn:c" />  
    </child1>  
</root>  
```  
  
 При размещении на объекте `child2` последовательность пространств имен (пространство имен, в котором располагается объект <xref:System.Xml.XPath.XPathNavigator> после вызова метода <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> и ряда вызовов метода <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A>) имеет следующий вид.  
  
- <xref:System.Xml.XPath.XPathNamespaceScope.All>: `xmlns:c="urn:c"`, `xmlns:a="urn:a"`, `xmlns=""`, `xmlns:b="http://www.contoso.com/b"`, `xmlns:a="http://www.contoso.com/a"`, `xmlns="http://www.contoso.com"` и `xmlns:xml="http://www.w3.org/XML/1998/namespace"`.  
  
- <xref:System.Xml.XPath.XPathNamespaceScope.ExcludeXml>: `xmlns:c="urn:c"`, `xmlns:a="urn:a"`, `xmlns=""`, `xmlns:b="http://www.contoso.com/b"`, `xmlns:a="http://www.contoso.com/a"` и `xmlns="http://www.contoso.com"`.  
  
- <xref:System.Xml.XPath.XPathNamespaceScope.Local>: `xmlns:c="urn:c"`.  
  
> [!NOTE]
> Класс <xref:System.Xml.XPath.XPathNavigator> возвращает узлы пространства имен в обратном порядке документа. Поэтому <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> существенно перемещается к последнему узлу пространства имен в текущей области видимости.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Обработка XML-данных с использованием модели данных XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Навигация в наборе узлов с помощью XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md)
- [Извлечение XML-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/extract-xml-data-using-xpathnavigator.md)
- [Доступ к XML-данным со строгой типизацией с помощью XPathNavigator](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
