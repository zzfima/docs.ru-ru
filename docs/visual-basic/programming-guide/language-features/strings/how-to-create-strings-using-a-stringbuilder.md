---
title: Инструкции. Создание строк с помощью StringBuilder
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 9295b9d0cdcfdb05dfc75f75f48c16c2354b09b0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344372"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Инструкции. Создание строк с помощью StringBuilder в Visual Basic

В этом примере создается длинная строка из множества меньших строк с помощью класса <xref:System.Text.StringBuilder>. Класс <xref:System.Text.StringBuilder> более эффективен, чем оператор `&=` для сцепления многих строк.

## <a name="example"></a>Пример

В следующем примере создается экземпляр класса <xref:System.Text.StringBuilder>, добавляются строки 1 000 в этот экземпляр, а затем возвращается строковое представление:

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a>См. также

- [Using the StringBuilder class](../../../../standard/base-types/stringbuilder.md) (Использование класса StringBuilder)
- [Оператор &=](../../../language-reference/operators/and-assignment-operator.md)
- [Строки](index.md)
- [Создание строк](../../../../standard/base-types/creating-new.md)
- [Операции со строками](../../../../standard/base-types/manipulating-strings.md)
