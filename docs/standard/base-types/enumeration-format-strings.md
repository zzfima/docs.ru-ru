---
title: "Строки форматов перечисления | Microsoft Docs"
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
  - "строки форматов перечисления"
  - "описатели формата, строки форматов перечисления"
  - "форматирование [платформа .NET Framework], перечисление"
ms.assetid: dd1ff672-1052-42cf-8666-4924fb6cd1a1
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Строки форматов перечисления
Можно использовать метод <xref:System.Enum.ToString%2A?displayProperty=fullName> для создания новой строки, представляющей числовое, шестнадцатеричное или строковое значение элемента перечисления.  Этот метод принимает строку формата перечисления, чтобы задать возвращаемое значение.  
  
 В следующей таблице приведены строки форматов перечисления и возвращаемые методом значения.  Спецификаторы формата не учитывают регистр.  
  
|Строка формата|Результат|  
|--------------------|---------------|  
|G или g|Отображает перечисление в виде строки, если это возможно. В противном случае отображает целочисленное значение текущего экземпляра.  Если для перечисления задан атрибут **Flags**, то строковые значения всех записей соединяются \(в качестве разделителя используется запятая\).  Если атрибут **Flags** не установлен, то неверное значение отображается в виде числовых записей.  В следующем примере показан спецификатор формата G.<br /><br /> [!code-csharp[Formatting.Enum#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)]
 [!code-vb[Formatting.Enum#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)]|  
|F или f|Отображает перечисление в виде строки, если это возможно.  Если перечисление полностью можно отобразить в виде строки как совокупность всех элементов перечисления \(даже если атрибут **Flags** не задан\), то строковые значения всех действительных записей соединяются \(в качестве разделителя используется запятая\).  Если значение не может быть определено по записям перечисления, то значение форматируется аналогично целому типу.  В следующем примере показан спецификатор формата F.<br /><br /> [!code-csharp[Formatting.Enum#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)]
 [!code-vb[Formatting.Enum#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)]|  
|D или d|Запись перечисления отображается в кратчайшем целочисленном представлении.  В следующем примере показан спецификатор формата D.<br /><br /> [!code-csharp[Formatting.Enum#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)]
 [!code-vb[Formatting.Enum#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)]|  
|X или x|Отображает перечисление в виде шестнадцатеричного значения.  При необходимости значение дополняется начальными пробелами, чтобы оно состояло как минимум из восьми знаков.  В следующем примере показан спецификатор формата X.<br /><br /> [!code-csharp[Formatting.Enum#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)]
 [!code-vb[Formatting.Enum#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)]|  
  
## Пример  
 В следующем примере определяется перечисление с именем `Colors`, состоящее из трех элементов: `Red`, `Blue` и `Green`.  
  
 [!code-csharp[Formatting.Enum#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#5)]
 [!code-vb[Formatting.Enum#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#5)]  
  
 После определения перечисления объявляется экземпляр.  
  
 [!code-csharp[Formatting.Enum#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#6)]
 [!code-vb[Formatting.Enum#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#6)]  
  
 Затем метод `Color.ToString(System.String)` можно использовать для отображения значений перечисления различными способами в зависимости от переданного спецификатора формата.  
  
 [!code-csharp[Formatting.Enum#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#7)]
 [!code-vb[Formatting.Enum#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#7)]  
  
## См. также  
 [Типы форматирования](../../../docs/standard/base-types/formatting-types.md)