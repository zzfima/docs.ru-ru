---
title: "Как: поток XML-фрагментов с доступом к сведениям заголовка (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: effd10df-87c4-4d7a-8a9a-1434d829dca5
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f745d0725b9b05620b4b967e51b452e54fe5e6d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-stream-xml-fragments-with-access-to-header-information-visual-basic"></a><span data-ttu-id="15fba-102">Как: поток XML-фрагментов с доступом к сведениям заголовка (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15fba-102">How to: Stream XML Fragments with Access to Header Information (Visual Basic)</span></span>
<span data-ttu-id="15fba-103">Иногда приходится считывать достаточно большие XML-файлы и разрабатывать приложения таким образом, чтобы объем памяти, используемой этим приложением, был прогнозируемым.</span><span class="sxs-lookup"><span data-stu-id="15fba-103">Sometimes you have to read arbitrarily large XML files, and write your application so that the memory footprint of the application is predictable.</span></span> <span data-ttu-id="15fba-104">Если попытаться заполнить XML-дерево большим XML-файлом, используемый объем памяти будет пропорционален размеру файла, то есть излишним.</span><span class="sxs-lookup"><span data-stu-id="15fba-104">If you attempt to populate an XML tree with a large XML file, your memory usage will be proportional to the size of the file—that is, excessive.</span></span> <span data-ttu-id="15fba-105">Поэтому следует вместо этого использовать потоки.</span><span class="sxs-lookup"><span data-stu-id="15fba-105">Therefore, you should use a streaming technique instead.</span></span>  
  
 <span data-ttu-id="15fba-106">Одна из возможностей состоит в том, чтобы разработать приложение с использованием метода <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="15fba-106">One option is to write your application using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="15fba-107">При этом для запроса XML-дерева можно использовать метод [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15fba-107">However, you might want to use [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to query the XML tree.</span></span> <span data-ttu-id="15fba-108">В этом случае можно написать собственный пользовательский метод оси.</span><span class="sxs-lookup"><span data-stu-id="15fba-108">If this is the case, you can write your own custom axis method.</span></span> <span data-ttu-id="15fba-109">Дополнительные сведения см. в разделе [как: запись метода оси XML (Visual Basic) LINQ](../../../../visual-basic/programming-guide/concepts/linq/how-to-write-a-linq-to-xml-axis-method.md).</span><span class="sxs-lookup"><span data-stu-id="15fba-109">For more information, see [How to: Write a LINQ to XML Axis Method (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-write-a-linq-to-xml-axis-method.md).</span></span>  
  
 <span data-ttu-id="15fba-110">Чтобы написать собственный метод оси, нужно написать небольшой метод, который использует метод <xref:System.Xml.XmlReader> для считывания узлов, до тех пор пока не достигнет одного из интересующих вас узлов.</span><span class="sxs-lookup"><span data-stu-id="15fba-110">To write your own axis method, you write a small method that uses the <xref:System.Xml.XmlReader> to read nodes until it reaches one of the nodes in which you are interested.</span></span> <span data-ttu-id="15fba-111">Затем метод вызывает метод <xref:System.Xml.Linq.XNode.ReadFrom%2A>, который читает из объекта <xref:System.Xml.XmlReader> и создает экземпляр фрагмента XML.</span><span class="sxs-lookup"><span data-stu-id="15fba-111">The method then calls <xref:System.Xml.Linq.XNode.ReadFrom%2A>, which reads from the <xref:System.Xml.XmlReader> and instantiates an XML fragment.</span></span> <span data-ttu-id="15fba-112">После этого можно написать запросы в LINQ на основе пользовательского метода оси.</span><span class="sxs-lookup"><span data-stu-id="15fba-112">You can then write LINQ queries on your custom axis method.</span></span>  
  
 <span data-ttu-id="15fba-113">Использование потоков лучше всего уместно в ситуациях, когда требуется обработать исходный документ только один раз, и элементы можно обрабатывать в порядке их следования в документе.</span><span class="sxs-lookup"><span data-stu-id="15fba-113">Streaming techniques are best applied in situations where you need to process the source document only once, and you can process the elements in document order.</span></span> <span data-ttu-id="15fba-114">Некоторые стандартные операторы запросов, например <xref:System.Linq.Enumerable.OrderBy%2A>, проходят через источник, собирают все данные, сортируют их и выдают первый элемент последовательности.</span><span class="sxs-lookup"><span data-stu-id="15fba-114">Certain standard query operators, such as <xref:System.Linq.Enumerable.OrderBy%2A>, iterate their source, collect all of the data, sort it, and then finally yield the first item in the sequence.</span></span> <span data-ttu-id="15fba-115">Обратите внимание, что, если вы используете оператор запроса, который материализует источник раньше, чем выбирает первый элемент, вы не сохраните малый объем используемой памяти.</span><span class="sxs-lookup"><span data-stu-id="15fba-115">Note that if you use a query operator that materializes its source before yielding the first item, you will not retain a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15fba-116">Пример</span><span class="sxs-lookup"><span data-stu-id="15fba-116">Example</span></span>  
 <span data-ttu-id="15fba-117">Иногда проблема становится немного интереснее.</span><span class="sxs-lookup"><span data-stu-id="15fba-117">Sometimes the problem gets just a little more interesting.</span></span> <span data-ttu-id="15fba-118">В следующем XML-документе потребитель пользовательского метода оси должен знать имя клиента, которому принадлежит каждый элемент.</span><span class="sxs-lookup"><span data-stu-id="15fba-118">In the following XML document, the consumer of your custom axis method also has to know the name of the customer that each item belongs to.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Root>  
  <Customer>  
    <Name>A. Datum Corporation</Name>  
    <Item>  
      <Key>0001</Key>  
    </Item>  
    <Item>  
      <Key>0002</Key>  
    </Item>  
    <Item>  
      <Key>0003</Key>  
    </Item>  
    <Item>  
      <Key>0004</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Fabrikam, Inc.</Name>  
    <Item>  
      <Key>0005</Key>  
    </Item>  
    <Item>  
      <Key>0006</Key>  
    </Item>  
    <Item>  
      <Key>0007</Key>  
    </Item>  
    <Item>  
      <Key>0008</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Southridge Video</Name>  
    <Item>  
      <Key>0009</Key>  
    </Item>  
    <Item>  
      <Key>0010</Key>  
    </Item>  
  </Customer>  
</Root>  
```  
  
 <span data-ttu-id="15fba-119">Подход, который используется в данном примере, также отслеживает эти данные о заголовках, сохраняет эти данные о заголовках, а затем строит небольшое XML-дерево, которое содержит и эти данные о заголовках, и сведения, которые вы перечисляете.</span><span class="sxs-lookup"><span data-stu-id="15fba-119">The approach that this example takes is to also watch for this header information, save the header information, and then build a small XML tree that contains both the header information and the detail that you are enumerating.</span></span> <span data-ttu-id="15fba-120">При использовании этого подхода метод оси позволяет получить это новое небольшое XML-дерево.</span><span class="sxs-lookup"><span data-stu-id="15fba-120">The axis method then yields this new, small XML tree.</span></span> <span data-ttu-id="15fba-121">Тогда запрос имеет доступ к данным о заголовках наряду с вашими сведениями.</span><span class="sxs-lookup"><span data-stu-id="15fba-121">The query then has access to the header information as well as the detail information.</span></span>  
  
 <span data-ttu-id="15fba-122">При данном подходе используется малый объем памяти.</span><span class="sxs-lookup"><span data-stu-id="15fba-122">This approach has a small memory footprint.</span></span> <span data-ttu-id="15fba-123">После того как выданы все данные фрагмента XML, ссылки на предыдущий фрагмент не сохраняются, и он становится пригодным для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="15fba-123">As each detail XML fragment is yielded, no references are kept to the previous fragment, and it is available for garbage collection.</span></span> <span data-ttu-id="15fba-124">Обратите внимание, что этот метод создает в куче много объектов с небольшим периодом жизни.</span><span class="sxs-lookup"><span data-stu-id="15fba-124">Note that this technique creates many short lived objects on the heap.</span></span>  
  
 <span data-ttu-id="15fba-125">В следующем примере показано, как реализовать и использовать пользовательский метод оси, который осуществляет потоковую передачу XML-фрагментов из файла, указанного в URI.</span><span class="sxs-lookup"><span data-stu-id="15fba-125">The following example shows how to implement and use a custom axis method that streams XML fragments from the file specified by the URI.</span></span> <span data-ttu-id="15fba-126">Эта пользовательская ось специально написана таким образом, что ожидает документа с элементами `Customer`, `Name` и `Item`, упорядоченными, как в указанном документе `Source.xml`.</span><span class="sxs-lookup"><span data-stu-id="15fba-126">This custom axis is specifically written such that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the above `Source.xml` document.</span></span> <span data-ttu-id="15fba-127">Это упрощенная реализация.</span><span class="sxs-lookup"><span data-stu-id="15fba-127">It is a simplistic implementation.</span></span> <span data-ttu-id="15fba-128">Будет подготовлена более надежная реализация анализа неверных документов.</span><span class="sxs-lookup"><span data-stu-id="15fba-128">A more robust implementation would be prepared to parse an invalid document.</span></span>  
  
```vb  
Module Module1  
  
    Sub Main()  
        Dim xmlTree = <Root>  
                          <%=  
                              From el In New StreamCustomerItem("Source.xml")  
                              Let itemKey = CInt(el.<Key>.Value)  
                              Where itemKey >= 3 AndAlso itemKey <= 7  
                              Select <Item>  
                                         <Customer><%= el.Parent.<Name>.Value %></Customer>  
                                         <%= el.<Key> %>  
                                     </Item>  
                          %>  
                      </Root>  
  
        Console.WriteLine(xmlTree)  
    End Sub  
  
End Module  
  
Public Class StreamCustomerItem  
    Implements IEnumerable(Of XElement)  
  
    Private _uri As String  
  
    Public Sub New(ByVal uri As String)  
        _uri = uri  
    End Sub  
  
    Public Function GetEnumerator() As IEnumerator(Of XElement) Implements IEnumerable(Of XElement).GetEnumerator  
        Return New StreamCustomerItemEnumerator(_uri)  
    End Function  
  
    Public Function GetEnumerator1() As IEnumerator Implements IEnumerable.GetEnumerator  
        Return Me.GetEnumerator()  
    End Function  
End Class  
  
Public Class StreamCustomerItemEnumerator  
    Implements IEnumerator(Of XElement)  
  
    Private _current As XElement  
    Private _customerName As String  
    Private _reader As Xml.XmlReader  
    Private _uri As String  
  
    Public Sub New(ByVal uri As String)  
        _uri = uri  
        _reader = Xml.XmlReader.Create(_uri)  
        _reader.MoveToContent()  
    End Sub  
  
    Public ReadOnly Property Current As XElement Implements IEnumerator(Of XElement).Current  
        Get  
            Return _current  
        End Get  
    End Property  
  
    Public ReadOnly Property Current1 As Object Implements IEnumerator.Current  
        Get  
            Return Me.Current  
        End Get  
    End Property  
  
    Public Function MoveNext() As Boolean Implements IEnumerator.MoveNext  
        Dim item As XElement  
        Dim name As XElement  
  
        ' Parse the file, save header information when encountered, and return the  
        ' current Item XElement.  
  
        ' loop through Customer elements  
        While _reader.Read()  
            If _reader.NodeType = Xml.XmlNodeType.Element Then  
                Select Case _reader.Name  
                    Case "Customer"  
                        ' move to Name element  
                        While _reader.Read()  
  
                            If _reader.NodeType = Xml.XmlNodeType.Element AndAlso  
                                _reader.Name = "Name" Then  
  
                                name = TryCast(XElement.ReadFrom(_reader), XElement)  
                                _customerName = If(name IsNot Nothing, name.Value, "")  
                                Exit While  
                            End If  
  
                        End While  
                    Case "Item"  
                        item = TryCast(XElement.ReadFrom(_reader), XElement)  
                        Dim tempRoot = <Root>  
                                           <Name><%= _customerName %></Name>  
                                           <%= item %>  
                                       </Root>  
                        _current = item  
                        Return True  
                End Select  
            End If  
        End While  
  
        Return False  
    End Function  
  
    Public Sub Reset() Implements IEnumerator.Reset  
        _reader = Xml.XmlReader.Create(_uri)  
        _reader.MoveToContent()  
    End Sub  
  
#Region "IDisposable Support"  
    Private disposedValue As Boolean ' To detect redundant calls  
  
    ' IDisposable  
    Protected Overridable Sub Dispose(ByVal disposing As Boolean)  
        If Not Me.disposedValue Then  
            If disposing Then  
                _reader.Close()  
            End If  
        End If  
        Me.disposedValue = True  
    End Sub  
  
    Public Sub Dispose() Implements IDisposable.Dispose  
        Dispose(True)  
        GC.SuppressFinalize(Me)  
    End Sub  
#End Region  
  
End Class  
```  
  
 <span data-ttu-id="15fba-129">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="15fba-129">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0003</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0004</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0005</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0006</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0007</Key>  
  </Item>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="15fba-130">См. также</span><span class="sxs-lookup"><span data-stu-id="15fba-130">See Also</span></span>  
 [<span data-ttu-id="15fba-131">Дополнительно LINQ to XML, программирования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15fba-131">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
