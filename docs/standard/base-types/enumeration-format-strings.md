---
title: Строки форматов перечисления
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- format specifiers, enumeration format strings
- enumeration format strings
- formatting [.NET Framework], enumeration
ms.assetid: dd1ff672-1052-42cf-8666-4924fb6cd1a1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 956dc7daad91d9daa3ac950d7f5897404dd314c2
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "44041269"
---
# <a name="enumeration-format-strings"></a>Строки форматов перечисления
Метод <xref:System.Enum.ToString%2A?displayProperty=nameWithType> можно использовать для создания новой строки, представляющей числовое, шестнадцатеричное или строковое значение элемента перечисления. Этот метод принимает строку формата перечисления, чтобы задать возвращаемое значение.

В следующей таблице приведены строки форматов перечисления и возвращаемые методом значения. Описатели формата не учитывают регистр.

| Строка форматирования | Результат |
| ------------- | ------ |
| G или g | Отображает перечисление в виде строкового значения, если это возможно. В противном случае отображает целочисленное значение текущего экземпляра. Если для перечисления задан атрибут **Flags**, строковые значения всех допустимых записей объединяются с запятой в качестве разделителя. Если атрибут **Flags** не задан, в виде числовой записи отображается недопустимое значение. В следующем примере показан описатель формата G.<br /><br />[!code-csharp[Formatting.Enum#1](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)] [!code-vb[Formatting.Enum#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)] |
| F или f | Отображает перечисление в виде строкового значения, если это возможно. Если перечисление полностью можно отобразить в виде строки как совокупность всех элементов перечисления (даже если атрибут **Flags** не задан), то строковые значения всех действительных записей объединяются с запятой в качестве разделителя. Если значение не может быть определено по записям перечисления, то значение форматируется аналогично целому типу. В следующем примере показан описатель формата F.<br /><br />[!code-csharp[Formatting.Enum#2](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)] [!code-vb[Formatting.Enum#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)] |
| D или d | Отображает запись перечисления в кратчайшем целочисленном представлении. В следующем примере показан описатель формата D.<br /><br />[!code-csharp[Formatting.Enum#3](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)] [!code-vb[Formatting.Enum#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)] |
| X или x | Отображает элемент перечисления в виде шестнадцатеричного значения. При необходимости значение дополняется начальными нулями, чтобы оно состояло как минимум из восьми знаков. В следующем примере показан описатель формата X.<br /><br /> [!code-csharp[Formatting.Enum#4](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)] [!code-vb[Formatting.Enum#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)] |

## <a name="example"></a>Пример

В следующем примере определяется перечисление с именем `Colors`, состоящее из трех элементов: `Red`, `Blue` и `Green`.

[!code-csharp[Formatting.Enum#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#5)]
[!code-vb[Formatting.Enum#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#5)]

После определения перечисления может быть объявлен, как показано далее.

[!code-csharp[Formatting.Enum#6](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#6)]
[!code-vb[Formatting.Enum#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#6)]

Затем метод `Color.ToString(System.String)` можно использовать для отображения значений перечисления различными способами в зависимости от переданного описателя формата.

[!code-csharp[Formatting.Enum#7](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#7)]
[!code-vb[Formatting.Enum#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#7)]

## <a name="see-also"></a>См. также

- [Типы форматирования](formatting-types.md)