---
title: Массивы параметров (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- parameter arrays [Visual Basic], about parameter arrays
- ParamArray keyword [Visual Basic], parameter arrays
- Visual Basic code, procedures
- parameters [Visual Basic], parameter arrays
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], indefinite number of argument values
- arrays [Visual Basic], parameter arrays
ms.assetid: c43edfae-9114-4096-9ebc-8c5c957a1067
ms.openlocfilehash: 372d5fdd2702d6f85f784ee5addea91abe46d3bd
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64639023"
---
# <a name="parameter-arrays-visual-basic"></a>Массивы параметров (Visual Basic)
Как правило не может вызвать процедуру с большим числом аргументов, чем ее объявлении. Если неопределенное число аргументов, можно объявить *массив параметров*, что позволяет процедуре принять массив значений для параметра. У вас не нужно знать число элементов в массиве параметров, при определении процедуры. Размер массива определяется отдельно при каждом вызове процедуры.  
  
## <a name="declaring-a-paramarray"></a>Объявление ParamArray  
 Использовании [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) ключевого слова для обозначения массива параметров в списке параметров. Действуют следующие правила.  
  
- Процедуры можно определить только один массив параметров, и он должен быть последним параметром в определении процедуры.  
  
- Массив параметров должен передаваться по значению. Это рекомендуется, чтобы явно включить [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) ключевое слово в определении процедуры.  
  
- Массив параметров автоматически является необязательным. Значением по умолчанию является пустой одномерный массив типа элемента в массиве параметров.  
  
- Все параметры, предшествующие в массиве параметров должны быть обязательными. Массив параметров должен быть единственным необязательным параметром.  
  
## <a name="calling-a-paramarray"></a>Вызов ParamArray  
 При вызове процедуры, определяющей массив параметров, можно указать аргумент одним из следующих способов:  
  
- Nothing, то есть можно опустить [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) аргумент. В этом случае пустой массив передается в процедуру. Вы также можете передать [Nothing](../../../../visual-basic/language-reference/nothing.md) ключевое слово, с тем же эффектом.  
  
- Список произвольное число аргументов, разделенных запятыми. Тип данных каждого аргумента должен быть неявно преобразуется в `ParamArray` тип элемента.  
  
- Массив с тем же типом элемента, как тип элемента в массиве параметров.  
  
 Во всех случаях код в процедуре рассматривает массив параметров как одномерный массив с элементами одного типа данных как `ParamArray` тип данных.  
  
> [!IMPORTANT]
>  Каждый раз, когда вы имеете дело с массив, который может быть неограниченно большим, есть риск переполнения некоторой внутренней емкости приложения. Если вы принимаете массив параметров, следует проверить размер массива, переданного ему вызывающий код. Предпринять соответствующие действия, если она слишком велика для приложения. Дополнительные сведения см. в разделе [массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="example"></a>Пример  
 В следующем примере определяет и вызывает функцию `calcSum`. `ParamArray` Модификатор параметра `args` позволяет принимать переменное число аргументов функции.  
  
 [!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]  
  
 Следующий пример определяет процедуру с массивом параметров и выводит значения всех элементов массива, переданного в массив параметров.  
  
 [!code-vb[VbVbcnProcedures#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#48)]  
  
 [!code-vb[VbVbcnProcedures#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#49)]  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [Процедуры](./index.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)
- [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md)
- [Необязательные параметры](./optional-parameters.md)
- [Перегрузка процедур](./procedure-overloading.md)
- [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Необязательный](../../../../visual-basic/language-reference/modifiers/optional.md)
