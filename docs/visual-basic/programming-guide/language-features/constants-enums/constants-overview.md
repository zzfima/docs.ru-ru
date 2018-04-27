---
title: Общие сведения о константах (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- constants [Visual Basic]
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 40330e8c2c60c866200e009a8280c7ec9c855435
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="constants-overview-visual-basic"></a>Общие сведения о константах (Visual Basic)
Константа представляет собой значимое имя, занимает место в число или строку, которая не изменяет. Константы хранят значения, которые, как названия, остаются неизменными во время выполнения приложения. Можно значительно улучшить читаемость кода и упростить обслуживание с помощью константы. Используйте их в коде, который содержит значения, или зависит от числа, которые трудно запомнить или осмыслить.  
  
## <a name="how-to-create-and-use-constants"></a>Создание и использование констант  
 Visual Basic содержит ряд предопределенных констант, в основном используемые для печати и отображения. Можно также создать собственные константы с `Const` инструкция, использующая те же правила, что для создания имени переменной. Если `Option Strict` — `On`, необходимо явно объявить тип константы.  
  
 Константа область, которая представляет собой весь код, на него можно ссылаться без указания полного имени, является таким же, как и для переменной, объявленной в том же расположении. Чтобы создать константу, которая существует в пределах определенной процедуры, объявите ее в этой процедуре. Чтобы создать константу, которая доступна по всему приложению, объявите его с помощью `Public` ключевое слово в раздел объявлений класса.  
  
> [!NOTE]
>  Несмотря на то, что константы напоминают переменные, нельзя изменять их и назначить новые значения их, как к переменным.  
  
 Константы, которые можно использовать в коде можно определить с помощью объектной модели для элементов управления или компонентов, которые работают с или они могут определяться пользователем (то есть, созданные вами).  
  
## <a name="compile-time-and-run-time-constants"></a>Константы времени компиляции и во время выполнения  
 Константы времени компиляции вычисляется во время компиляции кода, а константа времени выполнения может быть вычислена только во время выполнения приложения. Константы времени компиляции будет иметь то же значение при каждом выполнении приложения, а константа времени выполнения может меняться при каждом запуске. Константы времени компиляции необходимы для случаев, например границы массива, выражения case или инициализаторы.  
  
## <a name="in-this-section"></a>В этом разделе  
  
|Определение|Термин|  
|---|---|  
|[Практическое руководство. Объявление константы](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|Описание способов использования `Const` инструкцию, чтобы объявить константу и задать ей значение; объявляя константу, присвоить понятное имя значению.|  
|[Константы, определенные пользователем](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|Описание способов создания собственного константы, а также сведения о видимости и избегайте циклических ссылок.|  
|[Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|Предоставляет сведения о том, как компилятор Visual Basic инициализирует константы при `Option Explicit` отключена.|  
|[Практическое руководство. Группирование значений связанных констант](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|Показано, как группировать значения констант, которые связаны.|  
  
## <a name="reference"></a>Ссылка  
  
|Определение|Термин|  
|---|---|  
|[Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)|Список предопределенных констант в Visual Basic.|  
|[Оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md)|Описывает `Const` инструкции и его использование.|  
|[Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|Описывает `Option Strict` инструкции и его использование.|  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о перечислениях](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md) (Практическое руководство. Инициализация переменной массива в Visual Basic)
