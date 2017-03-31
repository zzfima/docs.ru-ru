---
title: "this (справочник по C#) | Документы Майкрософт"
description: "Ключевое слово this (справочник по C#)"
keywords: "this (C#), ключевое слово this (C#), ключевое слово this (справочник по C#), ключевое слово this (справочник по языку C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- this
- this_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
caps.latest.revision: 19
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8e14a32f11b9661ae18fd718fb1a72385fa7f3a7
ms.lasthandoff: 03/13/2017

---
# <a name="this-c-reference"></a>this (Справочник по C#)
Ключевое слово `this` ссылается на текущий экземпляр класса, а также используется в качестве модификатора первого параметра метода расширения.  
  
> [!NOTE]
>  В этой статье рассматривается использование `this` с экземплярами класса. Дополнительные сведения об использовании этого ключевого слова в методах расширения см. в разделе [Методы расширения](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).  
  
 Ниже перечислены наиболее частые способы использования `this`.  
  
-   Для квалификации элементов, скрытых одинаковыми именами, например:  
  
 [!code-cs[csrefKeywordsAccess#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_1.cs)]  
  
-   Для передачи другим методам объекта в качестве параметра, например:  
  
    ```  
    CalcTax(this);  
    ```  
  
-   Для объявления индексаторов, например:  
  
 [!code-cs[csrefKeywordsAccess#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_2.cs)]  
  
 У статических функций-членов нет указателя `this`, так как они существуют только на уровне класса и не являются частями объектов. Использование ссылки на `this` в статическом методе является недопустимым.  
  
## <a name="example"></a>Пример  
 В этом примере `this` используется для квалификации членов класса `Employee`, `name` и `alias`, которые скрыты одинаковыми именами. Это ключевое слово также используется для передачи объекта в метод `CalcTax`, который принадлежит другому классу.  
  
 [!code-cs[csrefKeywordsAccess#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_3.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [base](../../../csharp/language-reference/keywords/base.md)   
 [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md)
