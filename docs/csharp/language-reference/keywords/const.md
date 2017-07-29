---
title: "const (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- const_CSharpKeyword
- const
dev_langs:
- CSharp
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
caps.latest.revision: 28
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b8f6d567deed513ff5693fe39bd21c8607677402
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="const-c-reference"></a>const (Справочник по C#)
Для объявления константного поля или константной локальной используется ключевое слово `const`. Константные поля и локальные не являются переменными и не могут быть изменены. Константы могут быть числами, логическими значениями, строками или нулевыми ссылками. Не создавайте константу для предоставления сведений, которые могут измениться в любое время. Например, не используйте константное поле для хранения цены услуги, номера версии продукта или торгового названия компании. Эти значения могут со временем измениться, а поскольку константы распространяются компиляторами, для отражения изменений потребуется повторная компиляция остальных кодов, скомпилированных с использованием ваших библиотек. См. также описание ключевого слова [readonly](../../../csharp/language-reference/keywords/readonly.md). Пример:  
  
```csharp
const int x = 0;  
public const double gravitationalConstant = 6.673e-11;  
private const string productName = "Visual C#";  
```  
  
## <a name="remarks"></a>Примечания  
 Тип объявления константы указывает на тип членов, которые вводятся объявлением. Инициализатор константной локальной или константного поля должен быть выражением константы, поддерживающим явное преобразование в конечный тип.  
  
 Выражение константы — это выражение, которое можно полностью оценить во время компиляции. Таким образом, единственно возможными значениями для констант типов ссылок являются `string` и нулевые ссылки.  
  
 Объявление константы может объявлять несколько констант, например:  
  
```csharp
public const double x = 1.0, y = 2.0, z = 3.0;  
```  
  
 Модификатор `static` в объявлении константы не допускается.  
  
 Константа может участвовать в выражении константы следующим образом:  
  
```csharp
public const int c1 = 5;  
public const int c2 = c1 + 100;  
```  
  
> [!NOTE]
>  Ключевое слово [readonly](../../../csharp/language-reference/keywords/readonly.md) отличается от ключевого слова `const`. Поле `const` может быть инициализировано только при объявлении поля. Поле `readonly` может быть инициализировано при объявлении или в конструкторе. Таким образом, поля `readonly` могут иметь разные значения в зависимости от использованного конструктора. Также, несмотря на то, что поле `const` является константой во время компиляции, поле `readonly` можно использовать для констант во время выполнения, как в следующей строке: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`  
  
## <a name="example"></a>Пример  
 [!code-cs[csrefKeywordsModifiers#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_1.cs)]  
  
## <a name="example"></a>Пример  
 В этом примере показан способ использования констант в качестве локальных переменных.  
  
 [!code-cs[csrefKeywordsModifiers#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_2.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [readonly](../../../csharp/language-reference/keywords/readonly.md)

