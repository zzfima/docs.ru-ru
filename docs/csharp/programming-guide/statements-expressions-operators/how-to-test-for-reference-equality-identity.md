---
title: "Практическое руководство. Тестирование на равенство (идентичность) ссылок (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- object identity [C#]
- reference equality [C#]
ms.assetid: 91307fda-267b-4fd2-a338-2aada39ee791
caps.latest.revision: 13
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
ms.openlocfilehash: a115abe599f45163c0d7e6a31dd1dab3e9c06c4b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-test-for-reference-equality-identity-c-programming-guide"></a>Практическое руководство. Тестирование на равенство (идентичность) ссылок (Руководство по программированию на C#)
Вам не требуется реализовывать настраиваемую логику, чтобы обеспечить поддержку проверки ссылок на равенство в типах. Эту возможность для всех типов реализует метод <xref:System.Object.ReferenceEquals%2A?displayProperty=fullName>.  
  
 В следующем примере показано, как проверить две переменные на *равенство ссылок*, то есть как определить, ссылаются ли они на один и тот же объект в памяти.  
  
 В этом примере также показано, почему <xref:System.Object.ReferenceEquals%2A?displayProperty=fullName> всегда возвращает `false` для типов значений и почему не следует использовать <xref:System.Object.ReferenceEquals%2A> для проверки строк на равенство.  
  
## <a name="example"></a>Пример  
 [!code-cs[csProgGuideObjects#90](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-test-for-reference-equality-identity_1.cs)]  
  
 Реализация `Equals` в универсальном базовом классе <xref:System.Object?displayProperty=fullName> также выполняет проверку на равенство ссылок, однако использовать такой подход не рекомендуется, поскольку в случае переопределения метода в классе результат может отличаться от ожидаемого. Это справедливо также для операторов `==` и `!=`. При работе со ссылочными типами операторы == и `!=` по умолчанию выполняют проверку на равенство ссылок. Тем не менее производные классы могут перегружать оператор для проверки на равенство значений. Чтобы свести к минимуму вероятность появления ошибки, рекомендуется всегда использовать <xref:System.Object.ReferenceEquals%2A> в тех случаях, когда требуется проверить два объекта на равенство ссылок.  
  
 Константные строки в рамках одной сборки всегда интернируются во время выполнения. Таким образом, всегда присутствует только один экземпляр каждого уникального строкового литерала. Тем не менее во время выполнения не гарантируется интернирование строк, созданных во время выполнения, а также интернирование двух равных константных строк из разных сборок.  
  
## <a name="see-also"></a>См. также  
 [Сравнения на равенство](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)

