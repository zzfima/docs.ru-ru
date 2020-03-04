---
title: Сопоставление объектной иерархии с XML-данными
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 450e350b-6a68-4634-a2a5-33f4dc33baf0
ms.openlocfilehash: 642a7e5321d0150865f74a66a811914bc9f5d21d
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160031"
---
# <a name="mapping-the-object-hierarchy-to-xml-data"></a><span data-ttu-id="e54b0-102">Сопоставление объектной иерархии с XML-данными</span><span class="sxs-lookup"><span data-stu-id="e54b0-102">Mapping the Object Hierarchy to XML Data</span></span>
<span data-ttu-id="e54b0-103">Когда XML-документ находится в памяти, его концептуальным представлением является дерево.</span><span class="sxs-lookup"><span data-stu-id="e54b0-103">When an XML document is in memory, the conceptual representation is a tree.</span></span> <span data-ttu-id="e54b0-104">В распоряжении программиста имеется объектная иерархия для доступа к узлам этого дерева.</span><span class="sxs-lookup"><span data-stu-id="e54b0-104">For programming, you have an object hierarchy to access the nodes of the tree.</span></span> <span data-ttu-id="e54b0-105">Следующий пример показывает, как XML-содержимое становится узлами.</span><span class="sxs-lookup"><span data-stu-id="e54b0-105">The following example shows you how the XML content becomes nodes.</span></span>  
  
 <span data-ttu-id="e54b0-106">При считывании XML в модель DOM, его фрагменты преобразуются в узлы, и эти узлы сохраняют дополнительные метаданные о себе, в частности, тип узла и значения.</span><span class="sxs-lookup"><span data-stu-id="e54b0-106">As the XML is read into the XML Document Object Model (DOM), the pieces are translated into nodes, and these nodes retain additional metadata about themselves, such as their node type and values.</span></span> <span data-ttu-id="e54b0-107">Тип узла - это его объект и характеристики, определяющие выполняемые действия и свойства, которые можно установить и получить.</span><span class="sxs-lookup"><span data-stu-id="e54b0-107">The node type is its object and is what determines what actions can be performed and what properties can be set or retrieved.</span></span>  
  
 <span data-ttu-id="e54b0-108">Если имеется следующий простой XML:</span><span class="sxs-lookup"><span data-stu-id="e54b0-108">If you have the following simple XML:</span></span>  
  
 <span data-ttu-id="e54b0-109">**Ввод**</span><span class="sxs-lookup"><span data-stu-id="e54b0-109">**Input**</span></span>  
  
```xml  
<book>  
    <title>The Handmaid's Tale</title>  
</book>  
```  
  
 <span data-ttu-id="e54b0-110">Входные данные представлены в памяти следующим деревом узлов с назначенным свойством типа узлов:</span><span class="sxs-lookup"><span data-stu-id="e54b0-110">The input is represented in memory as the following node tree with the assigned node type property:</span></span>  
  
 <span data-ttu-id="e54b0-111">![Пример дерева узлов](../../../../docs/standard/data/xml/media/simple-xml.gif "Simple_XML")</span><span class="sxs-lookup"><span data-stu-id="e54b0-111">![example node tree](../../../../docs/standard/data/xml/media/simple-xml.gif "Simple_XML")</span></span>  
<span data-ttu-id="e54b0-112">Представление дерева узлов book и title</span><span class="sxs-lookup"><span data-stu-id="e54b0-112">Book and title node tree representation</span></span>  
  
 <span data-ttu-id="e54b0-113">Элемент `book` становится объектом **XmlElement**, следующий элемент `title` также становится объектом **XmlElement**, а элемент content становится объектом **XmlText**.</span><span class="sxs-lookup"><span data-stu-id="e54b0-113">The `book` element becomes an **XmlElement** object, the next element, `title`, also becomes an **XmlElement**, while the element content becomes an **XmlText** object.</span></span> <span data-ttu-id="e54b0-114">Методы и свойства объекта **XmlElement** отличаются от методов и свойств, доступных для объекта **XmlText**.</span><span class="sxs-lookup"><span data-stu-id="e54b0-114">In looking at the **XmlElement** methods and properties, the methods and properties are different than the methods and properties available on an **XmlText** object.</span></span> <span data-ttu-id="e54b0-115">Поэтому очень важно знать, какой тип узла получает XML, так как тип узла определяет действия, которые можно выполнить.</span><span class="sxs-lookup"><span data-stu-id="e54b0-115">So knowing what node type the XML markup becomes is vital, as its node type determines the actions that can be performed.</span></span>  
  
 <span data-ttu-id="e54b0-116">В следующих примерах выполняется считывание XML-данных и запись другого текста, в зависимости от типа узла.</span><span class="sxs-lookup"><span data-stu-id="e54b0-116">The following example reads in XML data and writes out different text, depending on the node type.</span></span> <span data-ttu-id="e54b0-117">Использование следующего XML-файла **items.xml** для получения входных данных.</span><span class="sxs-lookup"><span data-stu-id="e54b0-117">Using the following XML data file as input, **items.xml**:</span></span>  
  
 <span data-ttu-id="e54b0-118">**Ввод**</span><span class="sxs-lookup"><span data-stu-id="e54b0-118">**Input**</span></span>  
  
```xml  
<?xml version="1.0"?>  
<!-- This is a sample XML document -->  
<!DOCTYPE Items [<!ENTITY number "123">]>  
<Items>  
  <Item>Test with an entity: &number;</Item>  
  <Item>test with a child element <more/> stuff</Item>  
  <Item>test with a CDATA section <![CDATA[<456>]]> def</Item>  
  <Item>Test with a char entity: A</Item>  
  <!-- Fourteen chars in this element.-->  
  <Item>1234567890ABCD</Item>  
</Items>  
```  
  
 <span data-ttu-id="e54b0-119">Следующий пример кода считывает файл **items.xml** и отображает сведения о типах узлов.</span><span class="sxs-lookup"><span data-stu-id="e54b0-119">The following code example reads the **items.xml** file and displays information for each node type.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
    Private Const filename As String = "items.xml"  
  
    Public Shared Sub Main()  
  
        Dim reader As XmlTextReader = Nothing  
  
        Try  
            ' Load the reader with the data file and
            'ignore all white space nodes.
            reader = New XmlTextReader(filename)  
            reader.WhitespaceHandling = WhitespaceHandling.None  
  
            ' Parse the file and display each of the nodes.  
            While reader.Read()  
                Select Case reader.NodeType  
                    Case XmlNodeType.Element  
                        Console.Write("<{0}>", reader.Name)  
                    Case XmlNodeType.Text  
                        Console.Write(reader.Value)  
                    Case XmlNodeType.CDATA  
                        Console.Write("<![CDATA[{0}]]>", reader.Value)  
                    Case XmlNodeType.ProcessingInstruction  
                        Console.Write("<?{0} {1}?>", reader.Name, reader.Value)  
                    Case XmlNodeType.Comment  
                        Console.Write("<!--{0}-->", reader.Value)  
                    Case XmlNodeType.XmlDeclaration  
                        Console.Write("<?xml version='1.0'?>")  
                    Case XmlNodeType.Document  
                    Case XmlNodeType.DocumentType  
                        Console.Write("<!DOCTYPE {0} [{1}]", reader.Name, reader.Value)  
                    Case XmlNodeType.EntityReference  
                        Console.Write(reader.Name)  
                    Case XmlNodeType.EndElement  
                        Console.Write("</{0}>", reader.Name)  
                End Select  
            End While  
  
        Finally  
            If Not (reader Is Nothing) Then  
                reader.Close()  
            End If  
        End Try  
    End Sub 'Main ' End class  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
    private const String filename = "items.xml";  
  
    public static void Main()  
    {  
        XmlTextReader reader = null;  
  
        try  
        {  
            // Load the reader with the data file and ignore
            // all white space nodes.  
            reader = new XmlTextReader(filename);  
            reader.WhitespaceHandling = WhitespaceHandling.None;  
  
            // Parse the file and display each of the nodes.  
            while (reader.Read())  
            {  
                switch (reader.NodeType)  
                {  
                    case XmlNodeType.Element:  
                        Console.Write("<{0}>", reader.Name);  
                        break;  
                    case XmlNodeType.Text:  
                        Console.Write(reader.Value);  
                        break;  
                    case XmlNodeType.CDATA:  
                        Console.Write("<![CDATA[{0}]]>", reader.Value);  
                        break;  
                    case XmlNodeType.ProcessingInstruction:  
                        Console.Write("<?{0} {1}?>", reader.Name, reader.Value);  
                        break;  
                    case XmlNodeType.Comment:  
                        Console.Write("<!--{0}-->", reader.Value);  
                        break;  
                    case XmlNodeType.XmlDeclaration:  
                        Console.Write("<?xml version='1.0'?>");  
                        break;  
                    case XmlNodeType.Document:  
                        break;  
                    case XmlNodeType.DocumentType:  
                        Console.Write("<!DOCTYPE {0} [{1}]", reader.Name, reader.Value);  
                        break;  
                    case XmlNodeType.EntityReference:  
                        Console.Write(reader.Name);  
                        break;  
                    case XmlNodeType.EndElement:  
                        Console.Write("</{0}>", reader.Name);  
                        break;  
                }  
            }  
        }  
  
        finally  
        {  
            if (reader != null)  
                reader.Close();  
        }  
    }  
} // End class  
```  
  
 <span data-ttu-id="e54b0-120">Вывод примера содержит сопоставление данных типам узлов.</span><span class="sxs-lookup"><span data-stu-id="e54b0-120">The output from the example reveals the mapping of the data to the node types.</span></span>  
  
 <span data-ttu-id="e54b0-121">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="e54b0-121">**Output**</span></span>  
  
```xml  
<?xml version='1.0'?><!--This is a sample XML document --><!DOCTYPE Items [<!ENTITY number "123">]<Items><Item>Test with an entity: 123</Item><Item>test with a child element <more> stuff</Item><Item>test with a CDATA section <![CDATA[<456>]]> def</Item><Item>Test with a char entity: A</Item><--Fourteen chars in this element.--><Item>1234567890ABCD</Item></Items>  
```  
  
 <span data-ttu-id="e54b0-122">Рассматривая входные данные построчно и используя выход, сформированный кодом, можно использовать следующую таблицу для анализа того, какой узел сформировал конкретные строки результата, и понять, какие XML-данные стали соответствующими типами узлов.</span><span class="sxs-lookup"><span data-stu-id="e54b0-122">Taking the input one line at a time and using the output generated from the code, you can use the following table to analyze what node test generated which lines of output, thereby understanding what XML data became what kind of node type.</span></span>  
  
|<span data-ttu-id="e54b0-123">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e54b0-123">Input</span></span>|<span data-ttu-id="e54b0-124">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e54b0-124">Output</span></span>|<span data-ttu-id="e54b0-125">Проверка типа узла</span><span class="sxs-lookup"><span data-stu-id="e54b0-125">Node Type Test</span></span>|  
|-----------|------------|--------------------|  
|<span data-ttu-id="e54b0-126">\<?xml version="1.0"?></span><span class="sxs-lookup"><span data-stu-id="e54b0-126">\<?xml version="1.0"?></span></span>|<span data-ttu-id="e54b0-127">\<?xml version='1.0'?></span><span class="sxs-lookup"><span data-stu-id="e54b0-127">\<?xml version='1.0'?></span></span>|<span data-ttu-id="e54b0-128">XmlNodeType.XmlDeclaration</span><span class="sxs-lookup"><span data-stu-id="e54b0-128">XmlNodeType.XmlDeclaration</span></span>|  
|<span data-ttu-id="e54b0-129">\<!-- Это пример XML-документа --></span><span class="sxs-lookup"><span data-stu-id="e54b0-129">\<!-- This is a sample XML document --></span></span>|<span data-ttu-id="e54b0-130">\<!-- Это пример XML-документа --></span><span class="sxs-lookup"><span data-stu-id="e54b0-130">\<!--This is a sample XML document --></span></span>|<span data-ttu-id="e54b0-131">XmlNodeType.Comment</span><span class="sxs-lookup"><span data-stu-id="e54b0-131">XmlNodeType.Comment</span></span>|  
|<span data-ttu-id="e54b0-132">\<!DOCTYPE Items [\<!ENTITY number "123">]></span><span class="sxs-lookup"><span data-stu-id="e54b0-132">\<!DOCTYPE Items [\<!ENTITY number "123">]></span></span>|<span data-ttu-id="e54b0-133">\<!DOCTYPE Items [\<!ENTITY number "123">]></span><span class="sxs-lookup"><span data-stu-id="e54b0-133">\<!DOCTYPE Items [\<!ENTITY number "123">]</span></span>|<span data-ttu-id="e54b0-134">XmlNodeType.DocumentType</span><span class="sxs-lookup"><span data-stu-id="e54b0-134">XmlNodeType.DocumentType</span></span>|  
|<span data-ttu-id="e54b0-135">\<Items></span><span class="sxs-lookup"><span data-stu-id="e54b0-135">\<Items></span></span>|<span data-ttu-id="e54b0-136">\<Items></span><span class="sxs-lookup"><span data-stu-id="e54b0-136">\<Items></span></span>|<span data-ttu-id="e54b0-137">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="e54b0-137">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="e54b0-138">\<Item></span><span class="sxs-lookup"><span data-stu-id="e54b0-138">\<Item></span></span>|<span data-ttu-id="e54b0-139">\<Item></span><span class="sxs-lookup"><span data-stu-id="e54b0-139">\<Item></span></span>|<span data-ttu-id="e54b0-140">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="e54b0-140">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="e54b0-141">Проверка с помощью сущности: &number;</span><span class="sxs-lookup"><span data-stu-id="e54b0-141">Test with an entity: &number;</span></span>|<span data-ttu-id="e54b0-142">Test with an entity: 123</span><span class="sxs-lookup"><span data-stu-id="e54b0-142">Test with an entity: 123</span></span>|<span data-ttu-id="e54b0-143">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="e54b0-143">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="e54b0-144">\</Item></span><span class="sxs-lookup"><span data-stu-id="e54b0-144">\</Item></span></span>|<span data-ttu-id="e54b0-145">\</Item></span><span class="sxs-lookup"><span data-stu-id="e54b0-145">\</Item></span></span>|<span data-ttu-id="e54b0-146">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="e54b0-146">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="e54b0-147">\<Item></span><span class="sxs-lookup"><span data-stu-id="e54b0-147">\<Item></span></span>|<span data-ttu-id="e54b0-148">\<Item></span><span class="sxs-lookup"><span data-stu-id="e54b0-148">\<Item></span></span>|<span data-ttu-id="e54b0-149">XmNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="e54b0-149">XmNodeType.Element</span></span>|  
|<span data-ttu-id="e54b0-150">test with a child element</span><span class="sxs-lookup"><span data-stu-id="e54b0-150">test with a child element</span></span>|<span data-ttu-id="e54b0-151">test with a child element</span><span class="sxs-lookup"><span data-stu-id="e54b0-151">test with a child element</span></span>|<span data-ttu-id="e54b0-152">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="e54b0-152">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="e54b0-153">\<more></span><span class="sxs-lookup"><span data-stu-id="e54b0-153">\<more></span></span>|<span data-ttu-id="e54b0-154">\<more></span><span class="sxs-lookup"><span data-stu-id="e54b0-154">\<more></span></span>|<span data-ttu-id="e54b0-155">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="e54b0-155">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="e54b0-156">stuff</span><span class="sxs-lookup"><span data-stu-id="e54b0-156">stuff</span></span>|<span data-ttu-id="e54b0-157">stuff</span><span class="sxs-lookup"><span data-stu-id="e54b0-157">stuff</span></span>|<span data-ttu-id="e54b0-158">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="e54b0-158">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="e54b0-159">\</Item></span><span class="sxs-lookup"><span data-stu-id="e54b0-159">\</Item></span></span>|<span data-ttu-id="e54b0-160">\</Item></span><span class="sxs-lookup"><span data-stu-id="e54b0-160">\</Item></span></span>|<span data-ttu-id="e54b0-161">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="e54b0-161">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="e54b0-162">\<Item></span><span class="sxs-lookup"><span data-stu-id="e54b0-162">\<Item></span></span>|<span data-ttu-id="e54b0-163">\<Item></span><span class="sxs-lookup"><span data-stu-id="e54b0-163">\<Item></span></span>|<span data-ttu-id="e54b0-164">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="e54b0-164">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="e54b0-165">test with a CDATA section</span><span class="sxs-lookup"><span data-stu-id="e54b0-165">test with a CDATA section</span></span>|<span data-ttu-id="e54b0-166">test with a CDATA section</span><span class="sxs-lookup"><span data-stu-id="e54b0-166">test with a CDATA section</span></span>|<span data-ttu-id="e54b0-167">XmlTest.Text</span><span class="sxs-lookup"><span data-stu-id="e54b0-167">XmlTest.Text</span></span>|  
|<span data-ttu-id="e54b0-168"><![CDATA[\<456>]]\></span><span class="sxs-lookup"><span data-stu-id="e54b0-168"><![CDATA[\<456>]]\></span></span>|<span data-ttu-id="e54b0-169"><![CDATA[\<456>]]\></span><span class="sxs-lookup"><span data-stu-id="e54b0-169"><![CDATA[\<456>]]\></span></span>|<span data-ttu-id="e54b0-170">XmlTest.CDATA</span><span class="sxs-lookup"><span data-stu-id="e54b0-170">XmlTest.CDATA</span></span>|  
|<span data-ttu-id="e54b0-171">def</span><span class="sxs-lookup"><span data-stu-id="e54b0-171">def</span></span>|<span data-ttu-id="e54b0-172">def</span><span class="sxs-lookup"><span data-stu-id="e54b0-172">def</span></span>|<span data-ttu-id="e54b0-173">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="e54b0-173">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="e54b0-174">\</Item></span><span class="sxs-lookup"><span data-stu-id="e54b0-174">\</Item></span></span>|<span data-ttu-id="e54b0-175">\</Item></span><span class="sxs-lookup"><span data-stu-id="e54b0-175">\</Item></span></span>|<span data-ttu-id="e54b0-176">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="e54b0-176">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="e54b0-177">\<Item></span><span class="sxs-lookup"><span data-stu-id="e54b0-177">\<Item></span></span>|<span data-ttu-id="e54b0-178">\<Item></span><span class="sxs-lookup"><span data-stu-id="e54b0-178">\<Item></span></span>|<span data-ttu-id="e54b0-179">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="e54b0-179">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="e54b0-180">Проверка с помощью сущности char: &\#65;</span><span class="sxs-lookup"><span data-stu-id="e54b0-180">Test with a char entity: &\#65;</span></span>|<span data-ttu-id="e54b0-181">Test with a char entity: A</span><span class="sxs-lookup"><span data-stu-id="e54b0-181">Test with a char entity: A</span></span>|<span data-ttu-id="e54b0-182">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="e54b0-182">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="e54b0-183">\</Item></span><span class="sxs-lookup"><span data-stu-id="e54b0-183">\</Item></span></span>|<span data-ttu-id="e54b0-184">\</Item></span><span class="sxs-lookup"><span data-stu-id="e54b0-184">\</Item></span></span>|<span data-ttu-id="e54b0-185">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="e54b0-185">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="e54b0-186">\<!-- В этом элементе 14 элементов типа char.--></span><span class="sxs-lookup"><span data-stu-id="e54b0-186">\<!-- Fourteen chars in this element.--></span></span>|<span data-ttu-id="e54b0-187">\<-- В этом элементе 14 элементов типа char.--></span><span class="sxs-lookup"><span data-stu-id="e54b0-187">\<--Fourteen chars in this element.--></span></span>|<span data-ttu-id="e54b0-188">XmlNodeType.Comment</span><span class="sxs-lookup"><span data-stu-id="e54b0-188">XmlNodeType.Comment</span></span>|  
|<span data-ttu-id="e54b0-189">\<Item></span><span class="sxs-lookup"><span data-stu-id="e54b0-189">\<Item></span></span>|<span data-ttu-id="e54b0-190">\<Item></span><span class="sxs-lookup"><span data-stu-id="e54b0-190">\<Item></span></span>|<span data-ttu-id="e54b0-191">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="e54b0-191">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="e54b0-192">1234567890ABCD</span><span class="sxs-lookup"><span data-stu-id="e54b0-192">1234567890ABCD</span></span>|<span data-ttu-id="e54b0-193">1234567890ABCD</span><span class="sxs-lookup"><span data-stu-id="e54b0-193">1234567890ABCD</span></span>|<span data-ttu-id="e54b0-194">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="e54b0-194">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="e54b0-195">\</Item></span><span class="sxs-lookup"><span data-stu-id="e54b0-195">\</Item></span></span>|<span data-ttu-id="e54b0-196">\</Item></span><span class="sxs-lookup"><span data-stu-id="e54b0-196">\</Item></span></span>|<span data-ttu-id="e54b0-197">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="e54b0-197">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="e54b0-198">\</Items></span><span class="sxs-lookup"><span data-stu-id="e54b0-198">\</Items></span></span>|<span data-ttu-id="e54b0-199">\</Items></span><span class="sxs-lookup"><span data-stu-id="e54b0-199">\</Items></span></span>|<span data-ttu-id="e54b0-200">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="e54b0-200">XmlNodeType.EndElement</span></span>|  
  
 <span data-ttu-id="e54b0-201">Необходимо знать, какой тип узла назначен, так как от типа узла зависят допустимые типы действий и типы свойств, которые можно установить и получить.</span><span class="sxs-lookup"><span data-stu-id="e54b0-201">You must know what node type is assigned, as the node type controls what kinds of actions are valid and what kind of properties you can set and retrieve.</span></span>  
  
 <span data-ttu-id="e54b0-202">Управление созданием узлов для пробелов при загрузке данных в модель DOM осуществляется флагом **PreserveWhitespace**.</span><span class="sxs-lookup"><span data-stu-id="e54b0-202">Node creation for white space is controlled when the data is loaded into the DOM by the **PreserveWhitespace** flag.</span></span> <span data-ttu-id="e54b0-203">Дополнительные сведения см. в руководстве по [обработке незначимых и значимых пробелов при загрузке модели DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="e54b0-203">For more information, see [White Space and Significant White Space Handling when Loading the DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span></span>  
  
 <span data-ttu-id="e54b0-204">Чтобы добавить новые узлы в модель DOM, воспользуйтесь руководством [Вставка узлов в XML-документ](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="e54b0-204">To add new nodes to the DOM, see [Inserting Nodes into an XML Document](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md).</span></span> <span data-ttu-id="e54b0-205">Чтобы удалить узлы из модели DOM, изучите статью [Удаление узлов, содержимого и значений из XML-документа](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="e54b0-205">To remove nodes from the DOM, see [Removing Nodes, Content, and Values from an XML Document](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md).</span></span> <span data-ttu-id="e54b0-206">Чтобы изменить узлы в модели DOM, см. статью [Изменение узлов, содержимого и значений в XML-документе](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="e54b0-206">To modify the content of nodes in the DOM, see [Modifying Nodes, Content, and Values in an XML Document](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e54b0-207">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e54b0-207">See also</span></span>

- [<span data-ttu-id="e54b0-208">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="e54b0-208">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
