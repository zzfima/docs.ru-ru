---
title: "Создание новых строк в .NET"
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
helpviewer_keywords:
- CopyTo method
- Join method
- Format method
- Concat method
- strings [.NET Framework], creating
- Insert method
ms.assetid: 06fdf123-2fac-4459-8904-eb48ab908a30
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d000cd88fc9ee9fd48ef25e9bb4982688564a2a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="creating-new-strings-in-net"></a>Создание новых строк в .NET
[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Позволяет создавать с помощью простого присваивания строки, а также перегружать конструктор класса для создания строк с помощью нескольких различных параметров. [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Также предоставляет несколько методов в <xref:System.String?displayProperty=nameWithType> объектов путем объединения нескольких строк, массивов строк или объектов класса, создать новую строку.  
  
## <a name="creating-strings-using-assignment"></a>Создание строк с помощью присваивания  
 Самый простой способ создать новый <xref:System.String> объект — присвоить строковый литерал в <xref:System.String> объекта.  
  
## <a name="creating-strings-using-a-class-constructor"></a>Создание строк с помощью конструктора класса  
 Можно использовать перегрузки <xref:System.String> конструктор класса для создания строк из массивов знаков. Кроме того, строки можно создавать путем копирования того или иного знака указанное количество раз.  
  
## <a name="methods-that-return-strings"></a>Методы, возвращающие строки  
 В следующей таблице перечислено несколько полезных методов, которые возвращают строковые объекты.  
  
|Имя метода|Применение|  
|-----------------|---------|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|Создание форматированной строки из набора объектов ввода.|  
|<xref:System.String.Concat%2A?displayProperty=nameWithType>|Создание строк из двух или более строк.|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|Создание новой строки с помощью объединения массива строк.|  
|<xref:System.String.Insert%2A?displayProperty=nameWithType>|Создание новой строки с помощью вставки строки в указанную позицию существующей строки.|  
|<xref:System.String.CopyTo%2A?displayProperty=nameWithType>|Копирование указанных знаков в строке в указанную позицию в массиве символов.|  
  
### <a name="format"></a>Формат  
 Можно использовать **String.Format** метод для создания форматированных строк и соединения строк, представляющих несколько объектов. Этот метод автоматически преобразует в строку любой переданный объект. Например, если приложению необходимо отобразить **Int32** значение и **DateTime** значение для пользователя, легко создается строка для представления этих значений с помощью **формат**метод. Сведения о правилах форматирования, используемых в этом методе, см. в разделе [Составное форматирование](../../../docs/standard/base-types/composite-formatting.md).  
  
 В следующем примере используется **формат** метод для создания строки, содержащей целочисленную переменную.  
  
 [!code-csharp[Strings.Creating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#1)]
 [!code-vb[Strings.Creating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#1)]  
  
 В этом примере<xref:System.DateTime.Now%2A?displayProperty=nameWithType> отображает текущую дату и время в соответствии с языком и региональными параметрами, связанный с текущим потоком.  
  
### <a name="concat"></a>Concat  
 **String.Concat** метод может использоваться, чтобы легко создавать новый объект строки из двух или более существующих объектов. Он позволяет использовать независимый от языка способ сцепления строк. Этот метод принимает любой класс, производный от **System.Object**. В следующем примере создается строка из двух существующих объектов строки и символа разделителя.  
  
 [!code-csharp[Strings.Creating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#2)]
 [!code-vb[Strings.Creating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#2)]  
  
### <a name="join"></a>Join  
 **String.Join** метод создает новую строку из массива строк и разделителя строки. Этот метод полезен в случае необходимости сцепления нескольких строк и создания списка, отделенного, например, запятой.  
  
 В следующем примере используется пробел для привязки массива строк.  
  
 [!code-csharp[Strings.Creating#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#3)]
 [!code-vb[Strings.Creating#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#3)]  
  
### <a name="insert"></a>Insert  
 **String.Insert** метод создает новую строку с помощью вставки строки в указанной позиции в другую строку. Этот метод использует отсчитываемый от нуля индекс. В следующем примере строка вставляется в пятую позицию индекса `MyString`, и создается новая строка с этим значением.  
  
 [!code-csharp[Strings.Creating#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#4)]
 [!code-vb[Strings.Creating#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#4)]  
  
### <a name="copyto"></a>CopyTo  
 **String.CopyTo** метод копирует частей строки в массив символов. Можно указать начальный индекс строки и число копируемых символов. Для копирования этому методу необходимы исходный индекс, массив знаков, индекс назначения и число символов. Все индексы отсчитываются от нуля.  
  
 В следующем примере используется **CopyTo** метод копируемых символов слова «Hello» из строкового объекта в первую позицию индекса массива знаков.  
  
 [!code-csharp[Strings.Creating#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#5)]
 [!code-vb[Strings.Creating#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#5)]  
  
## <a name="see-also"></a>См. также  
 [Базовые операции со строками в .NET Framework](../../../docs/standard/base-types/basic-string-operations.md)  
 [Составное форматирование](../../../docs/standard/base-types/composite-formatting.md)
