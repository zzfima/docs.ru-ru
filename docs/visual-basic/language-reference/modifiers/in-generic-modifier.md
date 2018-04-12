---
title: In (универсальный модификатор) (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.VarianceIn
helpviewer_keywords:
- contravariance, In keyword [Visual Basic]
- In keyword [Visual Basic]
ms.assetid: 59bb13c5-fe96-42b8-8286-86293d1661c5
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 83e9aab4fc361754cfd750ae68f04b36dce13d0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="in-generic-modifier-visual-basic"></a>In (универсальный модификатор) (Visual Basic)
Для параметров универсального типа ключевое слово `In` указывает, что параметр типа является контравариантным.  
  
## <a name="remarks"></a>Примечания  
 Контравариантность позволяет использовать производные типы со степенью наследования меньше, чем у типа, заданного универсальным параметром. Благодаря этому можно осуществлять неявное преобразование классов, реализующих вариантные интерфейсы, и неявное преобразование типов делегатов.  
  
 Дополнительные сведения см. в разделе [Ковариация и контравариантность](../../programming-guide/concepts/covariance-contravariance/index.md).  
  
## <a name="rules"></a>Правила  
 Ключевое слово `In` может применяться в универсальных интерфейсах и делегатах.  
  
 Параметр типа может быть объявлен контравариантным в универсальный интерфейс или делегат, если она используется только в качестве типа аргументов метода и не используется в качестве типа возвращаемого значения метода. `ByRef`параметры не могут быть ковариантные или контравариантные.  
  
 Ковариация и контравариация поддерживаются для ссылочных типов и не поддерживается для типов значений.  
  
 В Visual Basic нельзя объявлять события в интерфейсах контравариантного без указания типа делегата. Кроме того контравариантный интерфейс не может включать вложенные классы, перечисления или структуры, но может включать вложенные интерфейсы.  
  
## <a name="behavior"></a>Поведение  
 Интерфейс с параметром контравариантного типа позволяет своим методам принимать аргументы производных типов, степень наследования у которых меньше, чем у параметра типа интерфейса. Например, поскольку в .NET Framework 4 в интерфейсе <xref:System.Collections.Generic.IComparer%601> тип T является ковариантным, можно присвоить объект типа `IComparer(Of Person)` объекту типа `IComparer(Of Employee)` без применения каких-либо специальных методов преобразования, если `Person` наследует `Employee`.  
  
 Контравариантный делегат может быть назначен другому делегату того же типа, но с производным параметром универсального типа меньшей степени.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как объявить, расширить и реализовать контравариантный универсальный интерфейс. В нем также показано, как можно использовать неявное преобразование для классов, реализующих этот интерфейс.  
  
 [!code-vb[vbVarianceKeywords#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/in-generic-modifier_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как объявить контравариантный универсальный делегат. В нем также показано, как можно выполнить неявное преобразование типа делегата.  
  
 [!code-vb[vbVarianceKeywords#2](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/in-generic-modifier_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Расхождение в универсальных интерфейсах](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
