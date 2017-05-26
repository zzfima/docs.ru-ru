---
title: "override (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- override
- override_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 44874332454d73da712a228c3eeeb58b0343e7e7
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="override-c-reference"></a>override (Справочник по C#)
Модификатор `override` требуется для расширения или изменения абстрактной или виртуальной реализации унаследованного метода, свойства, индексатора или события.  
  
## <a name="example"></a>Пример  
 В этом примере класс `Square` должен предоставить переопределенную реализацию `Area`, так как `Area` является унаследованным от абстрактного класса `ShapesClass`.  
  
 [!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_1.cs)]  
  
 Метод `override` предоставляет новую реализацию члена, унаследованного от базового класса. Метод, переопределенный объявлением `override`, называется переопределенным базовым методом. Переопределенный базовый метод должен иметь ту же сигнатуру, что и метод `override`. Дополнительные сведения о наследовании см. в разделе [Наследование](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  
  
 Невиртуальный или статический метод нельзя переопределить. Переопределенный базовый метод должен иметь тип `virtual`, `abstract` или `override`.  
  
 Объявление `override` не может изменить доступность метода `virtual`. Методы `override` и `virtual` должны иметь одинаковый [модификатор уровня доступа](../../../csharp/language-reference/keywords/access-modifiers.md).  
  
 Модификаторы `new`, `static` и `virtual` нельзя использовать для изменения метода `override`.  
  
 Переопределяющее объявление свойства должно задавать такие же модификатор уровня доступа, тип и имя, которые имеются у унаследованного свойства, а переопределенное свойство должно иметь тип `virtual`, `abstract` или `override`.  
  
 Дополнительные сведения об использовании ключевого слова `override` см. в разделах [Управление версиями с помощью ключевых слов Override и New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) и [Использование ключевых слов Override и New](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).  
  
## <a name="example"></a>Пример  
 В этом примере определяется базовый класс с именем `Employee` и производный класс с именем `SalesEmployee`. Класс `SalesEmployee` включает дополнительное свойство `salesbonus`, для использования которого переопределяется метод `CalculatePay`.  
  
 [!code-cs[csrefKeywordsModifiers#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_2.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Наследование](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [abstract](../../../csharp/language-reference/keywords/abstract.md)   
 [virtual](../../../csharp/language-reference/keywords/virtual.md)   
 [new](../../../csharp/language-reference/keywords/new.md)   
 [Полиморфизм](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)
