---
title: "base (Справочник по C#)"
description: "Сведения о ключевом слове base, которое используется для доступа к членам базового класса из производного класса в C#."
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- base
- BaseClass.BaseClass
- base_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- base keyword [C#]
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
caps.latest.revision: 14
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
ms.sourcegitcommit: 867f9eb286fa7ff5ef3e9167c1ab944c81161216
ms.openlocfilehash: b3a389d92373b6ba5995a7644b0440f9d8fad9ac
ms.contentlocale: ru-ru
ms.lasthandoff: 08/17/2017

---
# <a name="base-c-reference"></a>base (Справочник по C#)

Ключевое слово `base` используется для доступа к членам базового из производного класса в следующих случаях:

- Вызов метода базового класса, который был переопределен другим методом.

- Определение конструктора базового класса, который должен вызываться при создании экземпляров производного класса.

Доступ к базовому классу разрешен только в конструкторе, методе экземпляра или методе доступа к свойству экземпляра.

Использование ключевого слова `base` в статическом методе является недопустимым.

Доступ осуществляется к базовому классу, заданному в объявлении класса. Например, если указать `class ClassB : ClassA`, члены ClassA будут доступны из ClassB независимо от базового класса ClassA.

## <a name="example"></a>Пример
В приведенном ниже примере метод `Getinfo` присутствует как в базовом классе `Person`, так и в производном классе `Employee`. С помощью ключевого слова `base` можно вызвать метод `Getinfo` базового класса из производного класса.

[!code-cs[csrefKeywordsAccess#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_1.cs)]

Дополнительные примеры см. в разделах [new](../../../csharp/language-reference/keywords/new.md), [virtual](../../../csharp/language-reference/keywords/virtual.md) и [override](../../../csharp/language-reference/keywords/override.md).

## <a name="example"></a>Пример
В этом примере показано, как задать конструктор базового класса, вызываемый при создании экземпляров производного класса.

[!code-cs[csrefKeywordsAccess#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_2.cs)]

## <a name="c-language-specification"></a>Спецификация языка C#
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [this](../../../csharp/language-reference/keywords/this.md)
