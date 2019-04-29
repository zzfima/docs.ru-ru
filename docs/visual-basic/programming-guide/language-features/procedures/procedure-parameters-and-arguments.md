---
title: Параметры и аргументы процедуры (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], argument lists
- values [Visual Basic], passing to procedures
- arguments [Visual Basic], passing
- procedures [Visual Basic], parameters
- Visual Basic code, argument lists
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic procedures
- parameters [Visual Basic], lists
- arguments [Visual Basic], Visual Basic procedures
- arguments [Visual Basic], procedures
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- argument lists [Visual Basic]
- procedures [Visual Basic], parameter lists
ms.assetid: ff275aff-aa13-40df-bd4c-63486db8c1e9
ms.openlocfilehash: 80065cabcacdcf44b04fef7bacb978ca9c8077ae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791917"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a>Параметры и аргументы процедуры (Visual Basic)
В большинстве случаев процедура должна некоторые сведения об условиях ее возникновения, в которых она была вызвана. Процедура, выполняющая повторяющихся или общих задач использует различные сведения для каждого вызова. Эта информация состоит из переменных, констант и выражений, которые передаются в процедуру при ее вызове.  
  
 Объект *параметр* представляет значение, которое процедура ожидает предоставления при ее вызове. Объявление процедуры определяет его параметры.  
  
 Можно определить процедуру без параметров, один параметр или несколько. Часть определения процедуры, указывающей те параметры, называется *список параметров*.  
  
 *Аргумент* представляет значение, указываемое с параметром процедуры, при вызове процедуры. Вызывающий код предоставляет аргументы при вызове процедуры. Часть вызова процедуры, которая задает аргументы, называется *список аргументов*.  
  
 На следующем рисунке показан код вызова процедуры `safeSquareRoot` из двух различных местах. Первый вызов передает значение переменной `x` (4.0) в параметре `number`и возвращаемое значение в `root` (2.0) присваивается переменной `y`. Второй вызов передает значение литерала 9.0 для `number`и присваивает возвращаемое значение (3.0) переменной `z`.  
  
 ![Схема, показывающая передача аргумента в параметр](./media/procedure-parameters-and-arguments/pass-argument-parameter.gif)  
  
 Дополнительные сведения см. в разделе [различия между параметрами и аргументами](./differences-between-parameters-and-arguments.md).  
  
## <a name="parameter-data-type"></a>Тип данных параметра  
 Определить тип данных для параметра с помощью `As` предложение в его объявлении. Например следующая функция принимает строку и целое число.  
  
 [!code-vb[VbVbcnProcedures#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#32)]  
  
 Если переключатель проверки типа ([оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) является `Off,` `As` предложение является необязательным, за исключением того, что если используется в любой из параметров, его необходимо использовать все параметры. Если проверка типов `On`, `As` предложение является обязательным для всех параметров процедуры.  
  
 Если вызывающий код ожидает указания аргумента с типом данных, отличающемся от соответствующего параметра, такие как `Byte` для `String` параметр, он должен выполнить одно из следующих:  
  
- Указать только аргументы с типами данных, расширяющего преобразования к типу данных параметра;  
  
- Задайте `Option Strict Off` чтобы разрешить неявные сужающие преобразования; или  
  
- Используйте ключевые слова преобразования для явного преобразования типа данных.  
  
### <a name="type-parameters"></a>Параметры типа  
 Объект *универсальной процедуры* также определяет один или несколько *параметры типа* в дополнение к его обычным параметрам. Универсальная процедура позволяет вызывающему коду для передачи различных типов данных каждый раз при вызове процедуры, поэтому его можно настроить типы данных требованиям каждый отдельный вызов. См. раздел [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).  
  
## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Подпрограммы](./sub-procedures.md)
- [Процедуры функций](./function-procedures.md)
- [Процедуры свойств](./property-procedures.md)
- [Процедуры операторов](./operator-procedures.md)
- [Практическое руководство. Определение параметра для процедуры](./how-to-define-a-parameter-for-a-procedure.md)
- [Практическое руководство. Передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)
- [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)
- [Перегрузка процедур](./procedure-overloading.md)
- [Преобразование типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
