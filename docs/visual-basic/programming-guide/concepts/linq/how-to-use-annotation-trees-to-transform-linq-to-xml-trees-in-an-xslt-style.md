---
title: Практическое руководство. Использование примечаний для преобразования деревьев LINQ to XML в стиль XSLT
ms.date: 07/20/2015
ms.assetid: 08e91fa2-dac2-4463-9ef1-87b1ac3fa890
ms.openlocfilehash: d9cb32462535f099107343bd9069b4da3508c5b0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348357"
---
# <a name="how-to-use-annotations-to-transform-linq-to-xml-trees-in-an-xslt-style-visual-basic"></a>Как использовать аннотации для преобразования деревьев LINQ to XML в стиль XSLT (Visual Basic)

Заметки можно использовать для упрощения преобразований XML-дерева.

Некоторые XML-документы рассматриваются как «предназначенные для обработки в виде документов со смешанным содержимым». При использовании таких документов не требуется знать форму дочерних узлов элемента. Например, узел, содержащий текст, может выглядеть так:

```xml
<text>A phrase with <b>bold</b> and <i>italic</i> text.</text>
```

У любого заданного текстового узла может быть любое количество дочерних элементов `<b>` и `<i>`. Этот подход распространяется на ряд других ситуаций, таких как страницы, которые могут содержать различные дочерние элементы, такие как обычные абзацы, маркированные абзацы и точечные рисунки. Ячейки таблицы могут содержать текст, раскрывающиеся списки или битовые карты. Одной из основных отличительных особенностей кода XML, предназначенного для представления документов, является то, что неизвестно, какие дочерние элементы будет иметь тот или иной конкретный элемент.

Если требуется преобразовать элементы в дереве, о дочерних элементах которого знать не обязательно, то данный подход, использующий заметки, становится эффективным.

Сводка этого подхода состоит в следующем.

- Во-первых, обозначить элементы в дереве заметками в виде элемента замены.

- Во-вторых, провести итерацию по всему дереву, создавая новое дерево, в котором каждый элемент заменяется его заметкой. В этом примере реализуются итерация и создание нового дерева в функции с именем `XForm`.

В более подробном изложении этот подход состоит в следующем.

- Выполняются один или несколько запросов LINQ to XML, возвращающих набор элементов, которые требуется преобразовать из одной формы в другую. К каждому элементу запроса в качестве заметки добавляется новый объект <xref:System.Xml.Linq.XElement>. Новый элемент заменяет элемент с заметкой в новом, преобразованном дереве. Как видно из примера, этот код прост для написания.

- Новый элемент, добавляемый в виде заметки, может содержать новые дочерние узлы. Он может формировать поддерево любой необходимой формы.

- Предусмотрено специальное правило. Если дочерний узел нового элемента находится в другом пространстве имен, специально созданном для этой цели (в данном примере таким пространством имен является `http://www.microsoft.com/LinqToXmlTransform/2007`), то дочерний элемент не копируется в новое дерево. Вместо этого, если пространство имен представляет собой упомянутое выше специальное пространство имен, а локальным именем элемента является `ApplyTransforms`, последовательно производится итерация по дочерним узлам элемента в исходном дереве и копирование их в новое дерево (за исключением того, что обозначенные заметками дочерние элементы преобразуются сами согласно этим правилам).

- Это в какой-то мере аналогично спецификации преобразований в XSL. Запрос, выбирающий набор узлов, аналогичен выражению XPath для шаблона. Код создания нового элемента <xref:System.Xml.Linq.XElement>, сохраняемого в виде заметки, аналогичен конструктору последовательности в XSL, а элемент `ApplyTransforms` по своему назначению аналогичен элементу `xsl:apply-templates` в XSL.

- Одним из преимуществ данного подхода является то, что запросы при формировании всегда создаются применительно к неизмененному исходному дереву. Можно не беспокоиться о том, как изменения в дереве повлияют на формируемые запросы.

## <a name="transforming-a-tree"></a>Преобразование дерева

В первом примере все узлы `Paragraph` переименованы в `para`:

```vb
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">

Module Module1
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"

    Sub Main()
        Dim root As XElement = _
            <Root>
                <Paragraph>This is a sentence with <b>bold</b> and <i>italic</i> text.</Paragraph>
                <Paragraph>More text.</Paragraph>
            </Root>

        ' Replace Paragraph with p.
        For Each el In root...<Paragraph>
            ' same idea as xsl:apply-templates
            el.AddAnnotation( _
                <para>
                    <<%= at %>></>
                </para>)
        Next

        ' The XForm function, shown later in this topic, accomplishes the transform
        Dim newRoot As XElement = XForm(root)
        Console.WriteLine(newRoot)
    End Sub
End Module
```

 В этом примере выводятся следующие данные:

```xml
<Root>
  <para>This is a sentence with <b>bold</b> and <i>italic</i> text.</para>
  <para>More text.</para>
</Root>
```

## <a name="a-more-complicated-transform"></a>Более сложное преобразование

В следующем примере выполняется запрос к дереву и вычисляются среднее арифметическое и сумма элементов `Data`, а затем происходит их добавление в дерево в виде новых элементов.

```vb
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">

Module Module1
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"

    Sub Main()
        Dim data As XElement = _
            <Root>
                <Data>20</Data>
                <Data>10</Data>
                <Data>3</Data>
            </Root>

        ' While adding annotations, you can query the source tree all you want,
        ' as the tree is not mutated while annotating.
        data.AddAnnotation( _
            <Root>
                <<%= at %>/>
                <Average>
                    <%= _
                        String.Format("{0:F4}", _
                        data.Elements("Data") _
                        .Select(Function(z) CDec(z)).Average()) _
                    %>
                </Average>
                <Sum>
                    <%= _
                        data.Elements("Data").Select(Function(z) CInt(z)).Sum() _
                    %>
                </Sum>
            </Root> _
        )

        Console.WriteLine("Before Transform")
        Console.WriteLine("----------------")
        Console.WriteLine(data)
        Console.WriteLine(vbNewLine)

        ' The XForm function, shown later in this topic, accomplishes the transform
        Dim newData As XElement = XForm(data)

        Console.WriteLine("After Transform")
        Console.WriteLine("----------------")
        Console.WriteLine(newData)
    End Sub
End Module
```

В этом примере выводятся следующие данные:

```console
Before Transform
----------------
<Root>
  <Data>20</Data>
  <Data>10</Data>
  <Data>3</Data>
</Root>

After Transform
----------------
<Root>
  <Data>20</Data>
  <Data>10</Data>
  <Data>3</Data>
  <Average>11.0000</Average>
  <Sum>33</Sum>
</Root>
```

## <a name="effecting-the-transform"></a>Действие преобразования

Небольшая функция `XForm` создает новое преобразованное дерево из исходного дерева, обозначенного заметками.

Псевдокод для функции достаточно прост:

> Функция принимает элемент XElement в качестве аргумента и возвращает XElement.
>
> Если у элемента есть Аннотация XElement, то возвращается новый элемент XElement:
>
> - Имя нового объекта XElement является именем элемента заметки.
> - Все атрибуты копируются из заметки в новый узел.
> - Все дочерние узлы копируются из заметки, за исключением того, что определен специальный узел XF: Апплитрансформс, и выполняется итерация дочерних узлов исходного элемента. Если исходный дочерний узел не является XElement, он копируется в новое дерево. Если исходный дочерний элемент является XElement, то он преобразуется с помощью рекурсивного вызова этой функции.
>
> Если элемент не снабжен заметками:
>
> - Возврат нового элемента XElement
>   - Имя нового объекта XElement — это имя исходного элемента.
>   - Все атрибуты копируются из исходного элемента в элемент назначения.
>   - Все дочерние узлы копируются из исходного элемента.
>   - Если исходный дочерний узел не является XElement, он копируется в новое дерево. Если исходный дочерний элемент является XElement, то он преобразуется с помощью рекурсивного вызова этой функции.

Следующий код является реализацией этой функции:

```vb
' Build a transformed XML tree per the annotations.
Function XForm(ByVal source As XElement) As XElement
    If source.Annotation(Of XElement)() IsNot Nothing Then
        Dim anno As XElement = source.Annotation(Of XElement)()
        Return _
            <<%= anno.Name.ToString() %>>
                <%= anno.Attributes() %>
                <%= anno.Nodes().Select(Function(n As XNode) _
                    GetSubNodes(n, source)) %>
            </>
    Else
        Return _
            <<%= source.Name %>>
                <%= source.Attributes() %>
                <%= source.Nodes().Select(Function(n) GetExpandedNodes(n)) %>
            </>
    End If
End Function

Private Function GetSubNodes(ByVal n As XNode, ByVal s As XElement) As Object
    Dim annoEl As XElement = TryCast(n, XElement)
    If annoEl IsNot Nothing Then
        If annoEl.Name = at Then
            Return s.Nodes().Select(Function(n2 As XNode) GetExpandedNodes(n2))
        End If
    End If
    Return n
End Function

Private Function GetExpandedNodes(ByVal n2 As XNode) As XNode
    Dim e2 As XElement = TryCast(n2, XElement)
    If e2 Is Nothing Then
        Return n2
    Else
        Return XForm(e2)
    End If
End Function
```

## <a name="complete-example"></a>Полный пример

Следующий код является полным примером, включающим функцию `XForm`. Он включает несколько типичных вариантов использования преобразования данного типа:

```vb
Imports System.Collections.Generic
Imports System.Linq
Imports System.Text
Imports System.Xml
Imports System.Xml.Linq

Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">

Module Module1
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"

    ' Build a transformed XML tree per the annotations.
    Function XForm(ByVal source As XElement) As XElement
        If source.Annotation(Of XElement)() IsNot Nothing Then
            Dim anno As XElement = source.Annotation(Of XElement)()
            Return _
                <<%= anno.Name.ToString() %>>
                    <%= anno.Attributes() %>
                    <%= anno.Nodes().Select(Function(n As XNode) _
                        GetSubNodes(n, source)) %>
                </>
        Else
            Return _
                <<%= source.Name %>>
                    <%= source.Attributes() %>
                    <%= source.Nodes().Select(Function(n) GetExpandedNodes(n)) %>
                </>
        End If
    End Function

    Private Function GetSubNodes(ByVal n As XNode, ByVal s As XElement) As Object
        Dim annoEl As XElement = TryCast(n, XElement)
        If annoEl IsNot Nothing Then
            If annoEl.Name = at Then
                Return s.Nodes().Select(Function(n2 As XNode) GetExpandedNodes(n2))
            End If
        End If
        Return n
    End Function

    Private Function GetExpandedNodes(ByVal n2 As XNode) As XNode
        Dim e2 As XElement = TryCast(n2, XElement)
        If e2 Is Nothing Then
            Return n2
        Else
            Return XForm(e2)
        End If
    End Function

    Sub Main()
        Dim root As XElement = _
<Root Att1='123'>
    <!--A comment-->
    <Child>1</Child>
    <Child>2</Child>
    <Other>
        <GC>3</GC>
        <GC>4</GC>
    </Other>
    <SomeMixedContent>This is <i>an</i> element that <b>has</b> some mixed content</SomeMixedContent>
    <AnUnchangedElement>42</AnUnchangedElement>
</Root>

        ' Each of the following serves the same semantic purpose as
        ' XSLT templates and sequence constructors.

        ' Replace Child with NewChild.
        For Each el In root.<Child>
            el.AddAnnotation(<NewChild><%= CStr(el) %></NewChild>)
        Next

        ' Replace first GC with GrandChild, add an attribute.
        For Each el In root...<GC>.Take(1)
            el.AddAnnotation(<GrandChild ANewAttribute='999'><%= CStr(el) %></GrandChild>)
        Next

        ' Replace Other with NewOther, add new child elements around original content.
        For Each el In root.<Other>
            el.AddAnnotation( _
                <NewOther>
                    <MyNewChild>1</MyNewChild>
                    <<%= at %>></>
                    <ChildThatComesAfter/>
                </NewOther>)
        Next

        ' Change name of element that has mixed content.
        root...<SomeMixedContent>(0).AddAnnotation( _
                <MixedContent><<%= at %>></></MixedContent>)

        ' Replace <b> with <Bold>.
        For Each el In root...<b>
            el.AddAnnotation(<Bold><<%= at %>></></Bold>)
        Next

        ' Replace <i> with <Italic>.
        For Each el In root...<i>
            el.AddAnnotation(<Italic><<%= at %>></></Italic>)
        Next

        Console.WriteLine("Before Transform")
        Console.WriteLine("----------------")
        Console.WriteLine(root)
        Console.WriteLine(vbNewLine)
        Dim newRoot As XElement = XForm(root)

        Console.WriteLine("After Transform")
        Console.WriteLine("----------------")
        Console.WriteLine(newRoot)
    End Sub
End Module
```

В этом примере выводятся следующие данные:

```console
Before Transform
----------------
<Root Att1="123">
  <!--A comment-->
  <Child>1</Child>
  <Child>2</Child>
  <Other>
    <GC>3</GC>
    <GC>4</GC>
  </Other>
  <SomeMixedContent>This is <i>an</i> element that <b>has</b> some mixed content</SomeMixedContent>
  <AnUnchangedElement>42</AnUnchangedElement>
</Root>

After Transform
----------------
<Root Att1="123">
  <!--A comment-->
  <NewChild>1</NewChild>
  <NewChild>2</NewChild>
  <NewOther>
    <MyNewChild>1</MyNewChild>
    <GrandChild ANewAttribute="999">3</GrandChild>
    <GC>4</GC>
    <ChildThatComesAfter />
  </NewOther>
  <MixedContent>This is <Italic>an</Italic> element that <Bold>has</Bold> some mixed content</MixedContent>
  <AnUnchangedElement>42</AnUnchangedElement>
</Root>
```

## <a name="see-also"></a>См. также

- [Расширенное программирование LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
