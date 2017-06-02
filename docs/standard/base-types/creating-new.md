---
title: "Создание новых строк в .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Concat - метод"
  - "CopyTo - метод"
  - "Format - метод"
  - "Insert - метод"
  - "Join - метод"
  - "строки [платформа .NET Framework], создание"
ms.assetid: 06fdf123-2fac-4459-8904-eb48ab908a30
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Создание новых строк в .NET Framework
[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] позволяет создавать строки с помощью простой операции присваивания, а также перегружать конструктор класса для создания строк с помощью нескольких различных параметров.  Кроме того, в классе <xref:System.String?displayProperty=fullName> [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] имеются методы для создания строковых объектов путем объединения нескольких строк, массивов строк или объектов.  
  
## Создание строк с помощью присваивания  
 Самый простой способ создать новый объект <xref:System.String> — присвоить строковый литерал объекту <xref:System.String>.  
  
## Создание строк с помощью конструктора класса  
 С помощью перегруженных конструкторов класса <xref:System.String> можно создавать строки из массивов знаков.  Кроме того, строки можно создавать путем копирования того или иного знака указанное количество раз.  
  
## Методы, возвращающие строки  
 В следующей таблице перечислено несколько полезных методов, которые возвращают строковые объекты.  
  
|Название метода|Применение|  
|---------------------|----------------|  
|<xref:System.String.Format%2A?displayProperty=fullName>|Создание форматированной строки из набора объектов ввода.|  
|<xref:System.String.Concat%2A?displayProperty=fullName>|Создание строк из двух и более строк.|  
|<xref:System.String.Join%2A?displayProperty=fullName>|Создание новой строки с помощью объединения массива строк.|  
|<xref:System.String.Insert%2A?displayProperty=fullName>|Создание новой строки с помощью вставки строки в указанную позицию существующей строки.|  
|<xref:System.String.CopyTo%2A?displayProperty=fullName>|Копирование указанных знаков в строке в указанную позицию в массиве знаков.|  
  
### Формат  
 Метод **String.Format** используется для создания форматированных строк и соединения строк, представляющих несколько объектов.  Этот метод автоматически преобразует в строку любой переданный объект.  Например, если приложению необходимо отобразить для пользователя значение **Int32** и значение **DateTime**, легко создается строка для представления этих значений с помощью метода **Format**.  Сведения о правилах форматирования, используемых в этом методе, см. в разделе [Составное форматирование](../../../docs/standard/base-types/composite-formatting.md).  
  
 В следующем примере метод **Format** используется для создания строки, содержащей целочисленную переменную.  
  
 [!code-csharp[Strings.Creating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#1)]
 [!code-vb[Strings.Creating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#1)]  
  
 В этом примере значение <xref:System.DateTime.Now%2A?displayProperty=fullName> отображает текущие дату и время в соответствии с языком и региональными параметрами, связанными с текущим потоком.  
  
### Concat  
 Метод **String.Concat** используется для простого создания нового объекта строки из двух или более существующих объектов.  Он позволяет использовать независимый от языка способ сцепления строк.  Этот метод принимает любой класс, производный от **System.Object**.  В следующем примере создается строка из двух существующих объектов строки и знака разделения.  
  
 [!code-csharp[Strings.Creating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#2)]
 [!code-vb[Strings.Creating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#2)]  
  
### Join  
 Метод **String.Join** создает новую строку из массива строк и разделительной строки.  Этот метод полезен в случае необходимости сцепления нескольких строк и создания списка, отделенного, например, запятой.  
  
 В следующем примере используется пробел для привязки массива строк.  
  
 [!code-csharp[Strings.Creating#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#3)]
 [!code-vb[Strings.Creating#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#3)]  
  
### Атрибут Insert  
 Метод **String.Insert** создает новую строку с помощью вставки строки в указанную позицию другой строки.  Этот метод использует индекс с отсчетом от нуля.  В следующем примере строка вставляется в пятую позицию индекса `MyString`, и создается новая строка с этим значением.  
  
 [!code-csharp[Strings.Creating#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#4)]
 [!code-vb[Strings.Creating#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#4)]  
  
### CopyTo  
 Метод **String.CopyTo** копирует часть строки в массив знаков.  Можно указать начальный индекс строки и число копируемых знаков.  Для копирования этим методом необходимы исходный индекс, массив знаков, индекс назначения и число знаков.  Все индексы отсчитываются от нуля.  
  
 В следующем примере метод **CopyTo** используется для копирования знаков слова "Hello" из объекта строки в первую позицию индекса массива знаков.  
  
 [!code-csharp[Strings.Creating#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#5)]
 [!code-vb[Strings.Creating#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#5)]  
  
## См. также  
 [Основные операции со строками](../../../docs/standard/base-types/basic-string-operations.md)   
 [Составное форматирование](../../../docs/standard/base-types/composite-formatting.md)