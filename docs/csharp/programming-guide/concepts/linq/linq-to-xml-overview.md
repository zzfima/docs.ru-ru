---
title: Общие сведения о LINQ to XML (C#)
ms.date: 10/30/2018
ms.assetid: 716b94d3-0091-4de1-8e05-41bc069fa9dd
ms.openlocfilehash: 334788a50832b8fe42ecc9a3272dd71f2f2af4ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168419"
---
# <a name="linq-to-xml-overview-c"></a>Общие сведения о LINQ to XML (C#)

LINQ to XML обеспечивает интерфейс программирования для работы с XML в памяти на основе платформы .NET LINQ Framework. Интерфейс LINQ to XML использует возможности .NET и может быть сравним с обновленным, переработанным программным интерфейсом XML модели DOM.

XML широко используется для форматирования данных в целом ряде контекстов. Примеры XML можно обнаружить в веб-среде, в файлах конфигурации, в файлах Microsoft Office Word и в базах данных.

В [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] реализован современный пересмотренный подход к программированию средствами XML. Он позволяет изменять документы в оперативной памяти на основе модели DOM и поддерживает выражения запросов LINQ. Хотя в синтаксическом отношении эти выражения запросов отличаются от XPath, они предоставляют аналогичные функциональные возможности.

## <a name="linq-to-xml-developers"></a>Разработчики, использующие LINQ to XML

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] предназначен для различных категорий разработчиков. С точки зрения среднестатистического разработчика, заинтересованного в решении той или иной задачи, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] облегчает обработку XML, поскольку дает возможность получить опыт работы с запросами, аналогичный опыту работы с языком SQL. Посвятив совсем немного времени изучению предмета, программисты могут научиться составлять сжатые и мощные запросы на предпочитаемом ими языке программирования.

Профессиональные разработчики могут с помощью [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] существенно повысить производительность своего труда. Используя [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], они могут сократить объемы необходимого кода и сделать его более выразительным, более компактным и более мощным. Они могут одновременно использовать выражения запросов из нескольких доменов данных.

## <a name="what-is-linq-to-xml"></a>Что такое LINQ to XML?

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] — это выполняющийся в памяти интерфейс программирования XML с поддержкой LINQ, который позволяет работать с XML из языков программирования .NET Framework.

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] подобен модели DOM в том отношении, что загружает XML-документ в память. К такому документу можно направить запрос, его можно изменить, а после изменения его можно сохранить в файле или сериализовать и передать через Интернет. Но между [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] и моделью DOM существуют отличия: Интерфейс реализует облегченную и более простую в работе модель объектов; кроме того, в нем используются преимущества языковых возможностей, реализованные в C#.

Важнейшее достоинство [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] представлено интеграцией с LINQ. Эта интеграция дает возможность создавать запросы к загруженному в память XML-документу с целью получения коллекций элементов и атрибутов. По своей функциональности (но не по синтаксису) реализованные в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] возможности формирования запросов сопоставимы с возможностями XPath и XQuery. Интеграция LINQ в C# обеспечивает более строгую типизацию, проверку во время компиляции и улучшенную поддержку отладчика.

Другим преимуществом [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] является то, что возможность использования результатов запросов в качестве параметров конструкторов объектов <xref:System.Xml.Linq.XElement> и <xref:System.Xml.Linq.XAttribute> позволяет применять мощный подход для создания XML-деревьев. Этот подход, известный как *функциональное построение*, дает разработчикам возможность легко преобразовывать деревья XML из одной формы в другую.

Пусть имеется типичный заказ на покупку в формате XML, как это описано в статье [Пример XML-файла. Типичный заказ на покупку (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml-1.md). С помощью интерфейса [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] можно выполнить следующий запрос для получения значения атрибута артикула для каждого элемента в заказе на покупку:

```csharp
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load(purchaseOrderFilepath);

IEnumerable<string> partNos =  from item in purchaseOrder.Descendants("Item")
                               select (string) item.Attribute("PartNumber");
```

Это можно переписать в форме синтаксиса метода:

```csharp
IEnumerable<string> partNos = purchaseOrder.Descendants("Item").Select(x => (string) x.Attribute("PartNumber"));
```

Еще один пример. Пусть требуется сформировать отсортированный в соответствии с номерами деталей список продуктов стоимостью выше 100 долл. Для получения этих сведений можно выполнить следующий запрос:

```csharp
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load(purchaseOrderFilepath);

IEnumerable<XElement> pricesByPartNos =  from item in purchaseOrder.Descendants("Item")
                                 where (int) item.Element("Quantity") * (decimal) item.Element("USPrice") > 100
                                 orderby (string)item.Element("PartNumber")
                                 select item;
```

Опять же, это можно переписать в форме синтаксиса метода:

```csharp
IEnumerable<XElement> pricesByPartNos = purchaseOrder.Descendants("Item")
                                        .Where(item => (int)item.Element("Quantity") * (decimal)item.Element("USPrice") > 100)
                                        .OrderBy(order => order.Element("PartNumber"));
```

В дополнение к функциям, реализованным в LINQ, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] предоставляет усовершенствованный интерфейс программирования XML. Благодаря [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] появляются следующие возможности:

- Загрузка XML из [файлов](how-to-load-xml-from-a-file.md) или из [потоков](how-to-stream-xml-fragments-from-an-xmlreader.md).

- Сериализация XML в файлы или в потоки.

- Создание XML-кодов «с чистого листа» с помощью функционального построения.

- Обращение с запросами к XML с помощью XPath-подобных осей.

- Манипулирование загруженным в память XML-деревом с помощью таких методов, как <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A> и <xref:System.Xml.Linq.XElement.SetValue%2A>.

- Проверка XML-деревьев с помощью XSD.

- Использование сочетания этих функций для преобразования XML-деревьев из одной формы в другую.

## <a name="creating-xml-trees"></a>Создание деревьев XML

Одним из наиболее важных преимуществ программирования с использованием [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] является простота создания XML-деревьев. Так, для создания небольшого дерева XML можно написать следующий код:

```csharp
XElement contacts =
new XElement("Contacts",
    new XElement("Contact",
        new XElement("Name", "Patrick Hines"),
        new XElement("Phone", "206-555-0144",
            new XAttribute("Type", "Home")),
        new XElement("phone", "425-555-0145",
            new XAttribute("Type", "Work")),
        new XElement("Address",
            new XElement("Street1", "123 Main St"),
            new XElement("City", "Mercer Island"),
            new XElement("State", "WA"),
            new XElement("Postal", "68042")
        )
    )
);
```

Дополнительные сведения см. в разделе [Создание деревьев XML (C#)](./creating-xml-trees-linq-to-xml-2.md).

## <a name="see-also"></a>См. также

- [Ссылка (LINQ to XML)](./reference-linq-to-xml.md)
- [Сравнение LINQ to XML с моделью DOM (C#)](./linq-to-xml-vs-dom.md)
- [Сравнение LINQ to XML с другими XML-технологиями](./linq-to-xml-vs-other-xml-technologies.md)
- <xref:System.Xml.Linq>
