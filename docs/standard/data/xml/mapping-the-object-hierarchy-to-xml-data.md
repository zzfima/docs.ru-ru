---
title: "Сопоставление объектной иерархии с XML-данными"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 450e350b-6a68-4634-a2a5-33f4dc33baf0
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1bf43922fb702988e9057f541833cd58d33c820a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="mapping-the-object-hierarchy-to-xml-data"></a><span data-ttu-id="6695f-102">Сопоставление объектной иерархии с XML-данными</span><span class="sxs-lookup"><span data-stu-id="6695f-102">Mapping the Object Hierarchy to XML Data</span></span>
<span data-ttu-id="6695f-103">Когда XML-документ находится в памяти, его концептуальным представлением является дерево.</span><span class="sxs-lookup"><span data-stu-id="6695f-103">When an XML document is in memory, the conceptual representation is a tree.</span></span> <span data-ttu-id="6695f-104">В распоряжении программиста имеется объектная иерархия для доступа к узлам этого дерева.</span><span class="sxs-lookup"><span data-stu-id="6695f-104">For programming, you have an object hierarchy to access the nodes of the tree.</span></span> <span data-ttu-id="6695f-105">Следующий пример показывает, как XML-содержимое становится узлами.</span><span class="sxs-lookup"><span data-stu-id="6695f-105">The following example shows you how the XML content becomes nodes.</span></span>  
  
 <span data-ttu-id="6695f-106">При считывании XML в модель DOM, его фрагменты преобразуются в узлы, и эти узлы сохраняют дополнительные метаданные о себе, в частности, тип узла и значения.</span><span class="sxs-lookup"><span data-stu-id="6695f-106">As the XML is read into the XML Document Object Model (DOM), the pieces are translated into nodes, and these nodes retain additional metadata about themselves, such as their node type and values.</span></span> <span data-ttu-id="6695f-107">Тип узла - это его объект и характеристики, определяющие выполняемые действия и свойства, которые можно установить и получить.</span><span class="sxs-lookup"><span data-stu-id="6695f-107">The node type is its object and is what determines what actions can be performed and what properties can be set or retrieved.</span></span>  
  
 <span data-ttu-id="6695f-108">Если имеется следующий простой XML:</span><span class="sxs-lookup"><span data-stu-id="6695f-108">If you have the following simple XML:</span></span>  
  
 <span data-ttu-id="6695f-109">**Ввод**</span><span class="sxs-lookup"><span data-stu-id="6695f-109">**Input**</span></span>  
  
```xml  
<book>  
    <title>The Handmaid's Tale</title>  
</book>  
```  
  
 <span data-ttu-id="6695f-110">Входные данные представлены в памяти следующим деревом узлов с назначенным свойством типа узлов:</span><span class="sxs-lookup"><span data-stu-id="6695f-110">The input is represented in memory as the following node tree with the assigned node type property:</span></span>  
  
 <span data-ttu-id="6695f-111">![Пример узла дерева](../../../../docs/standard/data/xml/media/simple-xml.gif "Simple_XML")</span><span class="sxs-lookup"><span data-stu-id="6695f-111">![example node tree](../../../../docs/standard/data/xml/media/simple-xml.gif "Simple_XML")</span></span>  
<span data-ttu-id="6695f-112">Представление дерева узлов book и title</span><span class="sxs-lookup"><span data-stu-id="6695f-112">Book and title node tree representation</span></span>  
  
 <span data-ttu-id="6695f-113">`book` Элемент становится **XmlElement** объект, следующий элемент `title`, также становится **XmlElement**, а элемент content становится **XmlText** объекта.</span><span class="sxs-lookup"><span data-stu-id="6695f-113">The `book` element becomes an **XmlElement** object, the next element, `title`, also becomes an **XmlElement**, while the element content becomes an **XmlText** object.</span></span> <span data-ttu-id="6695f-114">Изучить **XmlElement** методы и свойства, методы и свойства отличаются от методов и свойств, доступных для **XmlText** объекта.</span><span class="sxs-lookup"><span data-stu-id="6695f-114">In looking at the **XmlElement** methods and properties, the methods and properties are different than the methods and properties available on an **XmlText** object.</span></span> <span data-ttu-id="6695f-115">Поэтому очень важно знать, какой тип узла получает XML, так как тип узла определяет действия, которые можно выполнить.</span><span class="sxs-lookup"><span data-stu-id="6695f-115">So knowing what node type the XML markup becomes is vital, as its node type determines the actions that can be performed.</span></span>  
  
 <span data-ttu-id="6695f-116">В следующих примерах выполняется считывание XML-данных и запись другого текста, в зависимости от типа узла.</span><span class="sxs-lookup"><span data-stu-id="6695f-116">The following example reads in XML data and writes out different text, depending on the node type.</span></span> <span data-ttu-id="6695f-117">Используя следующий XML-файл данных в качестве входных данных, **items.xml**:</span><span class="sxs-lookup"><span data-stu-id="6695f-117">Using the following XML data file as input, **items.xml**:</span></span>  
  
 <span data-ttu-id="6695f-118">**Ввод**</span><span class="sxs-lookup"><span data-stu-id="6695f-118">**Input**</span></span>  
  
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
  
 <span data-ttu-id="6695f-119">Следующий пример кода считывает **items.xml** и отображает сведения для каждого типа узла.</span><span class="sxs-lookup"><span data-stu-id="6695f-119">The following code example reads the **items.xml** file and displays information for each node type.</span></span>  
  
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
  
 <span data-ttu-id="6695f-120">Вывод примера содержит сопоставление данных типам узлов.</span><span class="sxs-lookup"><span data-stu-id="6695f-120">The output from the example reveals the mapping of the data to the node types.</span></span>  
  
 <span data-ttu-id="6695f-121">**Вывод**</span><span class="sxs-lookup"><span data-stu-id="6695f-121">**Output**</span></span>  
  
```xml  
<?xml version='1.0'?><!--This is a sample XML document --><!DOCTYPE Items [<!ENTITY number "123">]<Items><Item>Test with an entity: 123</Item><Item>test with a child element <more> stuff</Item><Item>test with a CDATA section <![CDATA[<456>]]> def</Item><Item>Test with a char entity: A</Item><--Fourteen chars in this element.--><Item>1234567890ABCD</Item></Items>  
```  
  
 <span data-ttu-id="6695f-122">Рассматривая входные данные построчно и используя выход, сформированный кодом, можно использовать следующую таблицу для анализа того, какой узел сформировал конкретные строки результата, и понять, какие XML-данные стали соответствующими типами узлов.</span><span class="sxs-lookup"><span data-stu-id="6695f-122">Taking the input one line at a time and using the output generated from the code, you can use the following table to analyze what node test generated which lines of output, thereby understanding what XML data became what kind of node type.</span></span>  
  
|<span data-ttu-id="6695f-123">Ввод</span><span class="sxs-lookup"><span data-stu-id="6695f-123">Input</span></span>|<span data-ttu-id="6695f-124">Вывод</span><span class="sxs-lookup"><span data-stu-id="6695f-124">Output</span></span>|<span data-ttu-id="6695f-125">Проверка типа узла</span><span class="sxs-lookup"><span data-stu-id="6695f-125">Node Type Test</span></span>|  
|-----------|------------|--------------------|  
|<span data-ttu-id="6695f-126">\<? версия xml = «1.0»? ></span><span class="sxs-lookup"><span data-stu-id="6695f-126">\<?xml version="1.0"?></span></span>|<span data-ttu-id="6695f-127">\<? версия xml = "1.0"? ></span><span class="sxs-lookup"><span data-stu-id="6695f-127">\<?xml version='1.0'?></span></span>|<span data-ttu-id="6695f-128">XmlNodeType.XmlDeclaration</span><span class="sxs-lookup"><span data-stu-id="6695f-128">XmlNodeType.XmlDeclaration</span></span>|  
|<span data-ttu-id="6695f-129">\<!--Это образец XML-документа--></span><span class="sxs-lookup"><span data-stu-id="6695f-129">\<!-- This is a sample XML document --></span></span>|<span data-ttu-id="6695f-130">\<!--Это образец XML-документа--></span><span class="sxs-lookup"><span data-stu-id="6695f-130">\<!--This is a sample XML document --></span></span>|<span data-ttu-id="6695f-131">XmlNodeType.Comment</span><span class="sxs-lookup"><span data-stu-id="6695f-131">XmlNodeType.Comment</span></span>|  
|<span data-ttu-id="6695f-132">\<! Элементы DOCTYPE [\<! СУЩНОСТИ номер «123» >] ></span><span class="sxs-lookup"><span data-stu-id="6695f-132">\<!DOCTYPE Items [\<!ENTITY number "123">]></span></span>|<span data-ttu-id="6695f-133">\<! Элементы DOCTYPE [\<! СУЩНОСТИ номер «123» >]</span><span class="sxs-lookup"><span data-stu-id="6695f-133">\<!DOCTYPE Items [\<!ENTITY number "123">]</span></span>|<span data-ttu-id="6695f-134">XmlNodeType.DocumentType</span><span class="sxs-lookup"><span data-stu-id="6695f-134">XmlNodeType.DocumentType</span></span>|  
|<span data-ttu-id="6695f-135">\<Элементы ></span><span class="sxs-lookup"><span data-stu-id="6695f-135">\<Items></span></span>|<span data-ttu-id="6695f-136">\<Элементы ></span><span class="sxs-lookup"><span data-stu-id="6695f-136">\<Items></span></span>|<span data-ttu-id="6695f-137">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="6695f-137">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="6695f-138">\<Item></span><span class="sxs-lookup"><span data-stu-id="6695f-138">\<Item></span></span>|<span data-ttu-id="6695f-139">\<Item></span><span class="sxs-lookup"><span data-stu-id="6695f-139">\<Item></span></span>|<span data-ttu-id="6695f-140">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="6695f-140">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="6695f-141">Тестирование с помощью сущности:&number;</span><span class="sxs-lookup"><span data-stu-id="6695f-141">Test with an entity: &number;</span></span>|<span data-ttu-id="6695f-142">Test with an entity: 123</span><span class="sxs-lookup"><span data-stu-id="6695f-142">Test with an entity: 123</span></span>|<span data-ttu-id="6695f-143">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="6695f-143">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="6695f-144">\</ Элемент ></span><span class="sxs-lookup"><span data-stu-id="6695f-144">\</Item></span></span>|<span data-ttu-id="6695f-145">\</ Элемент ></span><span class="sxs-lookup"><span data-stu-id="6695f-145">\</Item></span></span>|<span data-ttu-id="6695f-146">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="6695f-146">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="6695f-147">\<Item></span><span class="sxs-lookup"><span data-stu-id="6695f-147">\<Item></span></span>|<span data-ttu-id="6695f-148">\<Item></span><span class="sxs-lookup"><span data-stu-id="6695f-148">\<Item></span></span>|<span data-ttu-id="6695f-149">XmNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="6695f-149">XmNodeType.Element</span></span>|  
|<span data-ttu-id="6695f-150">test with a child element</span><span class="sxs-lookup"><span data-stu-id="6695f-150">test with a child element</span></span>|<span data-ttu-id="6695f-151">test with a child element</span><span class="sxs-lookup"><span data-stu-id="6695f-151">test with a child element</span></span>|<span data-ttu-id="6695f-152">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="6695f-152">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="6695f-153">\<Дополнительные ></span><span class="sxs-lookup"><span data-stu-id="6695f-153">\<more></span></span>|<span data-ttu-id="6695f-154">\<Дополнительные ></span><span class="sxs-lookup"><span data-stu-id="6695f-154">\<more></span></span>|<span data-ttu-id="6695f-155">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="6695f-155">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="6695f-156">stuff</span><span class="sxs-lookup"><span data-stu-id="6695f-156">stuff</span></span>|<span data-ttu-id="6695f-157">stuff</span><span class="sxs-lookup"><span data-stu-id="6695f-157">stuff</span></span>|<span data-ttu-id="6695f-158">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="6695f-158">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="6695f-159">\</ Элемент ></span><span class="sxs-lookup"><span data-stu-id="6695f-159">\</Item></span></span>|<span data-ttu-id="6695f-160">\</ Элемент ></span><span class="sxs-lookup"><span data-stu-id="6695f-160">\</Item></span></span>|<span data-ttu-id="6695f-161">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="6695f-161">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="6695f-162">\<Item></span><span class="sxs-lookup"><span data-stu-id="6695f-162">\<Item></span></span>|<span data-ttu-id="6695f-163">\<Item></span><span class="sxs-lookup"><span data-stu-id="6695f-163">\<Item></span></span>|<span data-ttu-id="6695f-164">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="6695f-164">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="6695f-165">test with a CDATA section</span><span class="sxs-lookup"><span data-stu-id="6695f-165">test with a CDATA section</span></span>|<span data-ttu-id="6695f-166">test with a CDATA section</span><span class="sxs-lookup"><span data-stu-id="6695f-166">test with a CDATA section</span></span>|<span data-ttu-id="6695f-167">XmlTest.Text</span><span class="sxs-lookup"><span data-stu-id="6695f-167">XmlTest.Text</span></span>|  
|<span data-ttu-id="6695f-168"><! [CDATA [\<456 >]]\></span><span class="sxs-lookup"><span data-stu-id="6695f-168"><![CDATA[\<456>]]\></span></span>|<span data-ttu-id="6695f-169"><! [CDATA [\<456 >]]\></span><span class="sxs-lookup"><span data-stu-id="6695f-169"><![CDATA[\<456>]]\></span></span>|<span data-ttu-id="6695f-170">XmlTest.CDATA</span><span class="sxs-lookup"><span data-stu-id="6695f-170">XmlTest.CDATA</span></span>|  
|<span data-ttu-id="6695f-171">def</span><span class="sxs-lookup"><span data-stu-id="6695f-171">def</span></span>|<span data-ttu-id="6695f-172">def</span><span class="sxs-lookup"><span data-stu-id="6695f-172">def</span></span>|<span data-ttu-id="6695f-173">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="6695f-173">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="6695f-174">\</ Элемент ></span><span class="sxs-lookup"><span data-stu-id="6695f-174">\</Item></span></span>|<span data-ttu-id="6695f-175">\</ Элемент ></span><span class="sxs-lookup"><span data-stu-id="6695f-175">\</Item></span></span>|<span data-ttu-id="6695f-176">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="6695f-176">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="6695f-177">\<Item></span><span class="sxs-lookup"><span data-stu-id="6695f-177">\<Item></span></span>|<span data-ttu-id="6695f-178">\<Item></span><span class="sxs-lookup"><span data-stu-id="6695f-178">\<Item></span></span>|<span data-ttu-id="6695f-179">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="6695f-179">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="6695f-180">Тест с помощью сущности char: &\#65;</span><span class="sxs-lookup"><span data-stu-id="6695f-180">Test with a char entity: &\#65;</span></span>|<span data-ttu-id="6695f-181">Test with a char entity: A</span><span class="sxs-lookup"><span data-stu-id="6695f-181">Test with a char entity: A</span></span>|<span data-ttu-id="6695f-182">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="6695f-182">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="6695f-183">\</ Элемент ></span><span class="sxs-lookup"><span data-stu-id="6695f-183">\</Item></span></span>|<span data-ttu-id="6695f-184">\</ Элемент ></span><span class="sxs-lookup"><span data-stu-id="6695f-184">\</Item></span></span>|<span data-ttu-id="6695f-185">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="6695f-185">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="6695f-186">\<!--В этом элементе 14 типов данных char.--></span><span class="sxs-lookup"><span data-stu-id="6695f-186">\<!-- Fourteen chars in this element.--></span></span>|<span data-ttu-id="6695f-187">\<— В этом элементе 14 типов данных char.--></span><span class="sxs-lookup"><span data-stu-id="6695f-187">\<--Fourteen chars in this element.--></span></span>|<span data-ttu-id="6695f-188">XmlNodeType.Comment</span><span class="sxs-lookup"><span data-stu-id="6695f-188">XmlNodeType.Comment</span></span>|  
|<span data-ttu-id="6695f-189">\<Item></span><span class="sxs-lookup"><span data-stu-id="6695f-189">\<Item></span></span>|<span data-ttu-id="6695f-190">\<Item></span><span class="sxs-lookup"><span data-stu-id="6695f-190">\<Item></span></span>|<span data-ttu-id="6695f-191">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="6695f-191">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="6695f-192">1234567890ABCD</span><span class="sxs-lookup"><span data-stu-id="6695f-192">1234567890ABCD</span></span>|<span data-ttu-id="6695f-193">1234567890ABCD</span><span class="sxs-lookup"><span data-stu-id="6695f-193">1234567890ABCD</span></span>|<span data-ttu-id="6695f-194">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="6695f-194">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="6695f-195">\</ Элемент ></span><span class="sxs-lookup"><span data-stu-id="6695f-195">\</Item></span></span>|<span data-ttu-id="6695f-196">\</ Элемент ></span><span class="sxs-lookup"><span data-stu-id="6695f-196">\</Item></span></span>|<span data-ttu-id="6695f-197">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="6695f-197">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="6695f-198">\</ Items ></span><span class="sxs-lookup"><span data-stu-id="6695f-198">\</Items></span></span>|<span data-ttu-id="6695f-199">\</ Items ></span><span class="sxs-lookup"><span data-stu-id="6695f-199">\</Items></span></span>|<span data-ttu-id="6695f-200">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="6695f-200">XmlNodeType.EndElement</span></span>|  
  
 <span data-ttu-id="6695f-201">Необходимо знать, какой тип узла назначен, так как от типа узла зависят допустимые типы действий и типы свойств, которые можно установить и получить.</span><span class="sxs-lookup"><span data-stu-id="6695f-201">You must know what node type is assigned, as the node type controls what kinds of actions are valid and what kind of properties you can set and retrieve.</span></span>  
  
 <span data-ttu-id="6695f-202">Управляет созданием узлов для пробелов при загрузке данных в модель DOM осуществляется **PreserveWhitespace** флаг.</span><span class="sxs-lookup"><span data-stu-id="6695f-202">Node creation for white space is controlled when the data is loaded into the DOM by the **PreserveWhitespace** flag.</span></span> <span data-ttu-id="6695f-203">Дополнительные сведения см. в разделе [пробелы обработка и значимых пробелов при загрузке модели DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="6695f-203">For more information, see [White Space and Significant White Space Handling when Loading the DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span></span>  
  
 <span data-ttu-id="6695f-204">Чтобы добавить новые узлы в модель DOM, в разделе [Вставка узлов в XML-документ](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="6695f-204">To add new nodes to the DOM, see [Inserting Nodes into an XML Document](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md).</span></span> <span data-ttu-id="6695f-205">Удаление узлов из DOM, в разделе [удаление узлов, содержимого и значений из XML-документа](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="6695f-205">To remove nodes from the DOM, see [Removing Nodes, Content, and Values from an XML Document](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md).</span></span> <span data-ttu-id="6695f-206">Чтобы изменить содержимое узлов в модели DOM, в разделе [изменение узлов, содержимого и значений в XML-документ](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="6695f-206">To modify the content of nodes in the DOM, see [Modifying Nodes, Content, and Values in an XML Document](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6695f-207">См. также</span><span class="sxs-lookup"><span data-stu-id="6695f-207">See Also</span></span>  
 [<span data-ttu-id="6695f-208">Модель объектов XML-документов (DOM)</span><span class="sxs-lookup"><span data-stu-id="6695f-208">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
