---
title: Потоковая передача фрагментов XML с доступом к сведениям заголовка (C#)
ms.date: 07/20/2015
ms.assetid: 7f242770-b0c7-418d-894b-643215e1f8aa
ms.openlocfilehash: 5bc10bcadae0e33ee63f953608ca841d44dd6527
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712394"
---
# <a name="how-to-stream-xml-fragments-with-access-to-header-information-c"></a><span data-ttu-id="03dd4-102">Потоковая передача фрагментов XML с доступом к сведениям заголовка (C#)</span><span class="sxs-lookup"><span data-stu-id="03dd4-102">How to stream XML fragments with access to header information (C#)</span></span>
<span data-ttu-id="03dd4-103">Иногда приходится считывать достаточно большие XML-файлы и разрабатывать приложения таким образом, чтобы объем памяти, используемой этим приложением, был прогнозируемым.</span><span class="sxs-lookup"><span data-stu-id="03dd4-103">Sometimes you have to read arbitrarily large XML files, and write your application so that the memory footprint of the application is predictable.</span></span> <span data-ttu-id="03dd4-104">Если попытаться заполнить XML-дерево большим XML-файлом, используемый объем памяти будет пропорционален размеру файла, то есть излишним.</span><span class="sxs-lookup"><span data-stu-id="03dd4-104">If you attempt to populate an XML tree with a large XML file, your memory usage will be proportional to the size of the file—that is, excessive.</span></span> <span data-ttu-id="03dd4-105">Поэтому следует вместо этого использовать потоки.</span><span class="sxs-lookup"><span data-stu-id="03dd4-105">Therefore, you should use a streaming technique instead.</span></span>  
  
<span data-ttu-id="03dd4-106">Одна из возможностей состоит в том, чтобы разработать приложение с использованием метода <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="03dd4-106">One option is to write your application using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="03dd4-107">При этом для создания запроса к XML-дереву можно использовать LINQ.</span><span class="sxs-lookup"><span data-stu-id="03dd4-107">However, you might want to use LINQ to query the XML tree.</span></span> <span data-ttu-id="03dd4-108">В этом случае можно написать собственный пользовательский метод оси.</span><span class="sxs-lookup"><span data-stu-id="03dd4-108">If this is the case, you can write your own custom axis method.</span></span> <span data-ttu-id="03dd4-109">См. сведения см. в руководстве по [созданию метода оси LINQ to XML (C#)](./how-to-write-a-linq-to-xml-axis-method.md).</span><span class="sxs-lookup"><span data-stu-id="03dd4-109">For more information, see [How to write a LINQ to XML axis method (C#)](./how-to-write-a-linq-to-xml-axis-method.md).</span></span>
  
 <span data-ttu-id="03dd4-110">Чтобы написать собственный метод оси, нужно написать небольшой метод, который использует метод <xref:System.Xml.XmlReader> для считывания узлов, до тех пор пока не достигнет одного из интересующих вас узлов.</span><span class="sxs-lookup"><span data-stu-id="03dd4-110">To write your own axis method, you write a small method that uses the <xref:System.Xml.XmlReader> to read nodes until it reaches one of the nodes in which you are interested.</span></span> <span data-ttu-id="03dd4-111">Затем метод вызывает метод <xref:System.Xml.Linq.XNode.ReadFrom%2A>, который читает из объекта <xref:System.Xml.XmlReader> и создает экземпляр фрагмента XML.</span><span class="sxs-lookup"><span data-stu-id="03dd4-111">The method then calls <xref:System.Xml.Linq.XNode.ReadFrom%2A>, which reads from the <xref:System.Xml.XmlReader> and instantiates an XML fragment.</span></span> <span data-ttu-id="03dd4-112">Затем он выдает фрагмент с помощью ключевого слова `yield return` методу, который выполняет перечисление по пользовательскому методу оси.</span><span class="sxs-lookup"><span data-stu-id="03dd4-112">It then yields each fragment through `yield return` to the method that is enumerating your custom axis method.</span></span> <span data-ttu-id="03dd4-113">После этого можно написать запросы в LINQ на основе пользовательского метода оси.</span><span class="sxs-lookup"><span data-stu-id="03dd4-113">You can then write LINQ queries on your custom axis method.</span></span>  
  
 <span data-ttu-id="03dd4-114">Использование потоков лучше всего уместно в ситуациях, когда требуется обработать исходный документ только один раз, и элементы можно обрабатывать в порядке их следования в документе.</span><span class="sxs-lookup"><span data-stu-id="03dd4-114">Streaming techniques are best applied in situations where you need to process the source document only once, and you can process the elements in document order.</span></span> <span data-ttu-id="03dd4-115">Некоторые стандартные операторы запросов, например <xref:System.Linq.Enumerable.OrderBy%2A>, проходят через источник, собирают все данные, сортируют их и выдают первый элемент последовательности.</span><span class="sxs-lookup"><span data-stu-id="03dd4-115">Certain standard query operators, such as <xref:System.Linq.Enumerable.OrderBy%2A>, iterate their source, collect all of the data, sort it, and then finally yield the first item in the sequence.</span></span> <span data-ttu-id="03dd4-116">Если вы используете оператор запроса, который материализует источник раньше, чем выбирает первый элемент, занимаемая память увеличится.</span><span class="sxs-lookup"><span data-stu-id="03dd4-116">If you use a query operator that materializes its source before yielding the first item, you will not retain a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03dd4-117">Пример</span><span class="sxs-lookup"><span data-stu-id="03dd4-117">Example</span></span>  

<span data-ttu-id="03dd4-118">Иногда проблема становится немного интереснее.</span><span class="sxs-lookup"><span data-stu-id="03dd4-118">Sometimes the problem gets just a little more interesting.</span></span> <span data-ttu-id="03dd4-119">В следующем XML-документе потребитель пользовательского метода оси должен знать имя клиента, которому принадлежит каждый элемент.</span><span class="sxs-lookup"><span data-stu-id="03dd4-119">In the following XML document, the consumer of your custom axis method also has to know the name of the customer that each item belongs to.</span></span>  
  
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
  
 <span data-ttu-id="03dd4-120">Подход, который используется в данном примере, также отслеживает эти данные о заголовках, сохраняет эти данные о заголовках, а затем строит небольшое XML-дерево, которое содержит и эти данные о заголовках, и сведения, которые вы перечисляете.</span><span class="sxs-lookup"><span data-stu-id="03dd4-120">The approach that this example takes is to also watch for this header information, save the header information, and then build a small XML tree that contains both the header information and the detail that you are enumerating.</span></span> <span data-ttu-id="03dd4-121">При использовании этого подхода метод оси позволяет получить это новое небольшое XML-дерево.</span><span class="sxs-lookup"><span data-stu-id="03dd4-121">The axis method then yields this new, small XML tree.</span></span> <span data-ttu-id="03dd4-122">Тогда запрос имеет доступ к данным о заголовках наряду с вашими сведениями.</span><span class="sxs-lookup"><span data-stu-id="03dd4-122">The query then has access to the header information as well as the detail information.</span></span>  
  
 <span data-ttu-id="03dd4-123">При данном подходе используется малый объем памяти.</span><span class="sxs-lookup"><span data-stu-id="03dd4-123">This approach has a small memory footprint.</span></span> <span data-ttu-id="03dd4-124">После того как выданы все данные фрагмента XML, ссылки на предыдущий фрагмент не сохраняются, и он становится пригодным для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="03dd4-124">As each detail XML fragment is yielded, no references are kept to the previous fragment, and it is available for garbage collection.</span></span> <span data-ttu-id="03dd4-125">Этот метод создает в куче много объектов с небольшим периодом жизни.</span><span class="sxs-lookup"><span data-stu-id="03dd4-125">This technique creates many short lived objects on the heap.</span></span>  
  
 <span data-ttu-id="03dd4-126">В следующем примере показано, как реализовать и использовать пользовательский метод оси, который осуществляет потоковую передачу XML-фрагментов из файла, указанного в URI.</span><span class="sxs-lookup"><span data-stu-id="03dd4-126">The following example shows how to implement and use a custom axis method that streams XML fragments from the file specified by the URI.</span></span> <span data-ttu-id="03dd4-127">Эта настраиваемая ось создана так, чтобы ожидать документ с элементами `Customer`, `Name` и `Item`, упорядоченными, как в указанном документе `Source.xml`.</span><span class="sxs-lookup"><span data-stu-id="03dd4-127">This custom axis is written such that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the above `Source.xml` document.</span></span> <span data-ttu-id="03dd4-128">Это упрощенная реализация.</span><span class="sxs-lookup"><span data-stu-id="03dd4-128">It is a simplistic implementation.</span></span> <span data-ttu-id="03dd4-129">Будет подготовлена более надежная реализация анализа неверных документов.</span><span class="sxs-lookup"><span data-stu-id="03dd4-129">A more robust implementation would be prepared to parse an invalid document.</span></span>  
  
```csharp  
static IEnumerable<XElement> StreamCustomerItem(string uri)  
{  
    using (XmlReader reader = XmlReader.Create(uri))  
    {  
        XElement name = null;  
        XElement item = null;  
  
        reader.MoveToContent();  
  
        // Parse the file, save header information when encountered, and yield the  
        // Item XElement objects as they are created.  
  
        // loop through Customer elements  
        while (reader.Read())  
        {  
            if (reader.NodeType == XmlNodeType.Element  
                && reader.Name == "Customer")  
            {  
                // move to Name element  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.Element &&  
                        reader.Name == "Name")  
                    {  
                        name = XElement.ReadFrom(reader) as XElement;  
                        break;  
                    }  
                }  
  
                // loop through Item elements  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.EndElement)  
                        break;  
                    if (reader.NodeType == XmlNodeType.Element  
                        && reader.Name == "Item")  
                    {  
                        item = XElement.ReadFrom(reader) as XElement;  
                        if (item != null) {  
                            XElement tempRoot = new XElement("Root",  
                                new XElement(name)  
                            );  
                            tempRoot.Add(item);  
                            yield return item;  
                        }  
                    }  
                }  
            }  
        }  
    }  
}  
  
static void Main(string[] args)  
{  
    XElement xmlTree = new XElement("Root",  
        from el in StreamCustomerItem("Source.xml")  
        where (int)el.Element("Key") >= 3 && (int)el.Element("Key") <= 7  
        select new XElement("Item",  
            new XElement("Customer", (string)el.Parent.Element("Name")),  
            new XElement(el.Element("Key"))  
        )  
    );  
    Console.WriteLine(xmlTree);  
}  
```  
  
 <span data-ttu-id="03dd4-130">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="03dd4-130">This code produces the following output:</span></span>  
  
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
