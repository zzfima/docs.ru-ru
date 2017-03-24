---
title: "Общие сведения о константах (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- constants
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8004045d233da0db017b26b350743ad9f8d61845
ms.lasthandoff: 03/13/2017

---
# <a name="constants-overview-visual-basic"></a>Общие сведения о константах (Visual Basic)
Константа представляет собой значимое имя, вместо числа или строки, которые не изменяются. Константы хранят значения, которые, как и предполагает название, остаются неизменными во время выполнения приложения. Можно значительно повысить читаемость кода и упростить поддержку, применяя константы. Их использование в коде, который содержит значения, или это зависит от числа, которые трудно запомнить или осмыслить.  
  
## <a name="how-to-create-and-use-constants"></a>Создание и использование констант  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]содержит ряд предопределенных констант, в основном используемые для печати и отображения. Можно также создать собственные константы с `Const` инструкция, использующая те же правила, что для создания имени переменной. Если `Option Strict` — `On`, необходимо явно объявлять тип константы.  
  
 Константа область, которая представляет собой набор весь код, на него можно ссылаться без указания полного имени, является таким же, как и для переменной, объявленной в том же расположении. Чтобы создать константу, которая существует в пределах определенной процедуры, объявите ее в этой процедуре. Чтобы создать константу, доступную в рамках всего приложения, объявите его с помощью `Public` ключевое слово в раздел объявлений класса.  
  
> [!NOTE]
>  Несмотря на то, что константы напоминают переменные, нельзя изменять их и присваивать новые значения для них, как к переменным.  
  
 Константы, которые можно использовать в коде можно определить с помощью объектной модели элементов управления или компонентов, работы с или они могут быть определяемой пользователем (то есть, созданные вами).  
  
## <a name="compile-time-and-run-time-constants"></a>Константы времени компиляции и во время выполнения  
 Константа времени компиляции вычисляется во время компиляции кода, а константа времени выполнения может быть вычислена только во время выполнения приложения. Константа времени компиляции будет иметь то же значение при каждом выполнении приложения, а константа времени выполнения может меняться при каждом запуске. Константы времени компиляции необходимы для случаев, таких как границы массива, условные выражения или инициализаторы.  
  
## <a name="in-this-section"></a>Содержание  
  
|Определение|Термин|  
|---|---|  
|[Практическое руководство. Объявление константы](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|Объясняется, как использовать `Const` инструкцию, чтобы объявить константу и задать его значение, объявив константу, присваивайте ей понятное имя, значение.|  
|[Константы, определенные пользователем](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|Описывает, как создавать собственные константы, включая сведения о видимости и как избежать циклических ссылок.|  
|[Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|Содержит сведения о том, как [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] инициализации констант компилятором при `Option Explicit` отключена.|  
|[Практическое руководство. Группирование значений связанных констант](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|Демонстрирует группировку постоянные значения, которые связаны.|  
  
## <a name="reference"></a>Ссылки  
  
|Определение|Термин|  
|---|---|  
|[Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)|Список предопределенных констант в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].|  
|[Оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md)|Описывает `Const` инструкции и его использования.|  
|[Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|Описывает `Option Strict` инструкции и его использования.|  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о перечислениях](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [Практическое руководство: инициализация переменной массива в Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
