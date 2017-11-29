---
title: "Option Infer - оператор"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.OptionInfer
- vb.Infer
helpviewer_keywords:
- variables [Visual Basic], declaring
- Option Infer statement [Visual Basic]
- Infer keyword [Visual Basic]
- declaring variables [Visual Basic], inferred
- inferred variable declaration
ms.assetid: 4ad3e6e9-8f5b-4209-a248-de22ef6e4652
caps.latest.revision: "72"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4634c198b5fc41a4834cbd3cd96f9d3f1863d09b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="option-infer-statement"></a>Option Infer - оператор
Включает использование локального определения типов при объявлении переменных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Option Infer { On | Off }  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`On`|Необязательно. Включает локальное определение типов.|  
|`Off`|Необязательно. Отключает локальное определение типов.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы задать `Option Infer` в файле, введите `Option Infer On` или `Option Infer Off` в начале файла перед всем остальным исходным кодом. Если значение, заданное для `Option Infer` в файле, конфликтует со значением, заданным в среде разработки или в командной строке, приоритет имеет значение в файле.  
  
 Если задать для `Option Infer` значение `On`, можно объявлять локальные переменные, не задавая явным образом тип данных. Компилятор определяет тип переменной по типу ее выражения инициализации.  
  
 На следующей иллюстрации `Option Infer` включен. Переменная в объявлении `Dim someVar = 2` объявляется как целочисленная определением типов.  
  
 ![IntelliSense-просмотров объявления. ] (../../../visual-basic/language-reference/statements/media/optioninferasinteger.png "optionInferAsInteger")  
IntelliSense при включенном параметре Option Infer  
  
 На следующей иллюстрации `Option Infer` отключен. Переменная в объявлении `Dim someVar = 2` объявляется как `Object` определением типов. В этом примере **Option Strict** принимает значение **Off** на [компиляция, конструктора проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).  
  
 ![IntelliSense-просмотров объявления. ] (../../../visual-basic/language-reference/statements/media/optioninferasobject.png "optionInferAsObject")  
IntelliSense при отключенном параметре Option Infer  
  
> [!NOTE]
>  Если переменная объявлена как `Object`, тип времени выполнения может измениться в ходе работы программы. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]выполняет операции *упаковка-преобразование* и *распаковки* для преобразования между `Object` и тип значения, что замедляет выполнение. Сведения об упаковке и распаковке см. в разделе [спецификация языка Visual Basic](../../../visual-basic/reference/language-specification/index.md).
  
 Определение типов применяется на уровне процедур и не применяется вне процедур в классах, структурах, модулях и интерфейсах.  
  
 Дополнительные сведения см. в разделе [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
## <a name="when-an-option-infer-statement-is-not-present"></a>Если оператор Option Infer отсутствует  
 Если исходный код не содержит `Option Infer` инструкции **Option Infer** на [компиляция, конструктора проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) используется. При использовании компилятора командной строки [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) используется параметр компилятора.  
  
#### <a name="to-set-option-infer-in-the-ide"></a>Чтобы включить Option Infer в среде разработки  
  
1.  Выберите проект в **обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. Дополнительные сведения см. в разделе [NIB: управление свойства проекта с помощью конструктора проектов](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).  
  
2.  Откройте вкладку **Компиляция**.  
  
3.  Задайте значение в **Option infer** поле.  
  
 При создании нового проекта **Option Infer** на **компиляции** набор вкладок **Option Infer** в **VB по умолчанию** диалоговое окно. Чтобы получить доступ к **VB по умолчанию** в диалоговом **средства** меню, нажмите кнопку **параметры**. В **параметры** диалогового окна разверните **проекты и решения**, а затем нажмите кнопку **VB по умолчанию**. Начальный параметр по умолчанию в **VB значения по умолчанию** — `On`.  
  
#### <a name="to-set-option-infer-on-the-command-line"></a>Чтобы включить Option Infer в командной строке  
  
-   Включить [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) параметра компилятора в **vbc** команды.  
  
## <a name="default-data-types-and-values"></a>Типы данных и значения по умолчанию  
 В следующей таблице перечислены результаты различных сочетаний заданных типов данных и инициализаторов в операторе `Dim`.  
  
|Указан тип данных?|Указан инициализатор?|Пример|Результат|  
|---|---|---|---|  
|Нет|Нет|`Dim qty`|Если `Option Strict` отключен (по умолчанию), для переменной устанавливается значение `Nothing`.<br /><br /> Если параметр `Option Strict` включен, при компиляции возникает ошибка.|  
|Нет|Да|`Dim qty = 5`|Если параметр `Option Infer` включен (по умолчанию), переменная получает тип данных инициализатора. В разделе [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Если параметры `Option Infer` и `Option Strict` отключены, переменная получает тип данных `Object`.<br /><br /> Если параметр `Option Infer` отключен, а параметр `Option Strict` включен, при компиляции возникает ошибка.|  
|Да|Нет|`Dim qty As Integer`|Переменная инициализируется со значением по умолчанию для типа данных. Дополнительные сведения см. в разделе [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).|  
|Да|Да|`Dim qty  As Integer = 5`|Если тип данных инициализатора нельзя преобразовать в указанный тип данных, возникает ошибка времени компиляции.|  
  
## <a name="example"></a>Пример  
 В следующих примерах показано, как оператор `Option Infer` включает локальное определение типов.  
  
 [!code-vb[VbVbalrTypeInference#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано, что тип времени выполнения может различаться, когда переменная указана как `Object`.  
  
 [!code-vb[VbVbalrTypeInference#11](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)  
 [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [Упаковка-преобразование и распаковка-преобразование](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
