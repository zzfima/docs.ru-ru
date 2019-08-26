---
title: Как выполнить явную реализацию членов двух интерфейсов (руководство по программированию на C#)
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: 1d4dd0485be1d859e3e9594ab1558a907b8f1f7a
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589194"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a>Как выполнить явную реализацию членов двух интерфейсов (руководство по программированию на C#)
Явная реализация [интерфейсов](../../language-reference/keywords/interface.md) позволяет разработчику реализовать два интерфейса с одинаковыми именами членов и создать отдельные реализации каждого члена интерфейса. В этом примере размеры поля выводятся в метрической и английской системе мер. [Класс](../../language-reference/keywords/class.md) Box реализует два интерфейса (IEnglishDimensions и IMetricDimensions), представляющие соответствующие системы мер. В обоих интерфейсах представлены члены с одинаковыми именами: Length и Width.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideInheritance#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#9)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Если требуется использовать единицы английской системы мер по умолчанию, реализуйте методы Length и Width обычным способом, после чего явно реализуйте методы Length и Width из интерфейса IMetricDimensions:  
  
 [!code-csharp[csProgGuideInheritance#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#10)]  
  
 В этом случае единицы английской системы мер будут доступны из экземпляра класса, а метрические единицы — из экземпляра интерфейса:  
  
 [!code-csharp[csProgGuideInheritance#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#11)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Классы и структуры](../classes-and-structs/index.md)
- [Интерфейсы](./index.md)
- [Практическое руководство. Явная реализация элементов интерфейса](./how-to-explicitly-implement-interface-members.md)
