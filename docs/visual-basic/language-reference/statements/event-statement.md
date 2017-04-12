---
title: "Оператор Event | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Event
- vb.Custom
dev_langs:
- VB
helpviewer_keywords:
- Event statement
- declaring events, syntax
- Public keyword, Event statements
- Custom keyword
- declarations, events
- event keyword [Visual Basic]
- WithEvents keyword, Event statements
- events [Visual Basic], declaring
- ByVal keyword, Event statements
- events [Visual Basic], custom
- ByRef keyword, Event statements
- declaring user-defined events
ms.assetid: 306ff8ed-74dd-4b6a-bd2f-e91b17474042
caps.latest.revision: 33
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: b0ea8074f996622df3cd88a7e87fc1156b63dcaf
ms.lasthandoff: 03/13/2017

---
# <a name="event-statement"></a>Оператор Event
Объявляет пользовательское событие.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ <attrlist> ] [ accessmodifier ] _  
[ Shared ] [ Shadows ] Event eventname[(parameterlist)] _  
[ Implements implementslist ]  
' -or-  
[ <attrlist> ] [ accessmodifier ] _  
[ Shared ] [ Shadows ] Event eventname As delegatename _  
[ Implements implementslist ]  
' -or-  
 [ <attrlist> ] [ accessmodifier ] _  
[ Shared ] [ Shadows ] Custom Event eventname As delegatename _  
[ Implements implementslist ]  
   [ <attrlist> ] AddHandler(ByVal value As delegatename)  
      [ statements ]  
   End AddHandler  
   [ <attrlist> ] RemoveHandler(ByVal value As delegatename)  
      [ statements ]  
   End RemoveHandler  
   [ <attrlist> ] RaiseEvent(delegatesignature)  
      [ statements ]  
   End RaiseEvent  
End Event  
```  
  
## <a name="parts"></a>Части  
  
|Отделение|Описание|  
|---|---|  
|`attrlist`|Необязательный. Список атрибутов, применимых к этому событию. Несколько атрибутов разделяются запятыми. Необходимо заключить [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md) в угловые скобки («`<`«и»`>`»).|  
|`accessmodifier`|Необязательный. Указывает, какой код может получать доступ к событию. Ниже указаны доступные значения.<br /><br /> -   [Открытый](../../../visual-basic/language-reference/modifiers/public.md)— доступ к нему любой код, который можно получить доступ к элементу, который объявляет его.<br />-   [Защищенные](../../../visual-basic/language-reference/modifiers/protected.md)— только код внутри своего класса или производного класса есть доступ к нему.<br />-   [Дружественные](../../../visual-basic/language-reference/modifiers/friend.md)— только для кода в той же сборке есть доступ к нему.<br />-   [Закрытый](../../../visual-basic/language-reference/modifiers/private.md)— доступ к нему только код внутри элемента, объявляющего его.<br /><br /> Можно указать `Protected Friend` для предоставления доступа из кода в классе события, производном классе или той же сборке.|  
|`Shared`|Необязательный. Указывает, что это событие не связано с определенным экземпляром класса или структуры.|  
|`Shadows`|Необязательный. Указывает, что это событие повторно объявляет и скрывает программные элементы с одинаковыми именами или набор перегруженных элементов в базовом классе. Можно скрыть любой тип объявленного элемента, используя любой другой тип.<br /><br /> Скрытый элемент недоступен из производного класса, который его скрывает, за исключением тех классов, из которых недоступен скрывающий элемент. Например, если элемент `Private` скрывает элемент базового класса, то код, у которого нет разрешений на доступ к элементу `Private`, получает доступ к элементу базового класса.|  
|`eventname`|Обязательный. Имя события; соответствует стандартным правилам именования переменных.|  
|`parameterlist`|Необязательный. Список локальных переменных, которые представляют параметры этого события. Необходимо заключить [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md) в круглые скобки.|  
|`Implements`|Необязательный. Указывает, что это событие реализует событие интерфейса.|  
|`implementslist`|Является обязательным, если предоставлен параметр `Implements`. Список реализуемых процедур `Sub`. Несколько процедур разделяются запятыми.<br /><br /> *реализуемая_процедура* [, *реализуемая_процедура* ...]<br /><br /> Каждый элемент `implementedprocedure` имеет перечисленные ниже синтаксис и компоненты.<br /><br /> `interface`.`definedname`<br /><br /> -   `interface`— Обязательный параметр. Имя интерфейса, реализуемого классом или структурой, содержащими эту процедуру.<br />-   `Definedname`— Обязательный параметр. Имя, под которым процедура определена в `interface`. Оно не должно совпадать с `name`, именем, которое эта процедура использует для реализации определенной процедуры.|  
|`Custom`|Обязательный. События, объявленные как `Custom`, должны определять настраиваемые методы доступа `AddHandler`, `RemoveHandler` и `RaiseEvent`.|  
|`delegatename`|Необязательный. Имя делегата, указывающего подпись обработчика событий.|  
|`AddHandler`|Обязательный. Объявляет метод доступа `AddHandler`, который задает операторы, выполняемые при добавлении обработчика событий, явно с помощью оператора `AddHandler` или неявно с помощью предложения `Handles`.|  
|`End AddHandler`|Обязательный. Завершает блок `AddHandler`.|  
|`value`|Обязательный. Имя параметра.|  
|`RemoveHandler`|Обязательный. Объявляет метод доступа `RemoveHandler`, который задает операторы, выполняемые при удалении обработчика событий с помощью оператора `RemoveHandler`.|  
|`End RemoveHandler`|Обязательный. Завершает блок `RemoveHandler`.|  
|`RaiseEvent`|Обязательный. Объявляет метод доступа `RaiseEvent`, который задает операторы, выполняемые при создании события с помощью оператора `RaiseEvent`. Как правило, при этом вызывается список делегатов, обслуживаемых методами доступа `AddHandler` и `RemoveHandler`.|  
|`End RaiseEvent`|Обязательный. Завершает блок `RaiseEvent`.|  
|`delegatesignature`|Обязательный. Список параметров, соответствующий параметрам, требуемым делегатом `delegatename`. Необходимо заключить [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md) в круглые скобки.|  
|`statements`|Необязательный. Операторы, содержащие тела методов `AddHandler`, `RemoveHandler` и `RaiseEvent`.|  
|`End Event`|Обязательный. Завершает блок `Event`.|  
  
## <a name="remarks"></a>Примечания  
 После объявления события используйте оператор `RaiseEvent` для создания события. Типичные события можно объявлять и создавать, как показано в следующих фрагментах кода.  
  
 [!code-vb[VbVbalrEvents&#13;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/event-statement_1.vb)]  
  
> [!NOTE]
>  Аргументы событий можно объявлять так же, как аргументы процедур, за следующими исключениями: события не могут иметь именованные аргументы, аргументы `ParamArray` и аргументы `Optional`. События не имеют возвращаемых значений.  
  
 Для обработки события его необходимо связать с подпрограммой обработчика событий с помощью оператора `Handles` или `AddHandler`. Подписи подпрограммы и события должны совпадать. Для обработки общего события необходимо использовать оператор `AddHandler`.  
  
 `Event` можно использовать только на уровне модуля. Это означает *контекст объявления* события должен быть класс, структура, модуль или интерфейс и не может быть исходным файлом, пространство имен, процедуры или блока. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 В большинстве случаев для объявления события можно использовать первый пример синтаксиса в разделе "Синтаксис" этой статьи. Однако в некоторых сценариях требуется контролировать поведение события более детально. Последний пример синтаксиса в разделе "Синтаксис" этой статьи, в котором используется ключевое слово `Custom`, обеспечивает такие возможности, позволяя определять настраиваемые события. В настраиваемом событии можно точно указать, что происходит, когда код добавляет или удаляет обработчик события для события или когда код вызывает событие. Примеры см. в разделе [как: объявление пользовательских событий для экономии памяти](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md) и [как: объявление пользовательских событий для избежать блокировки](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md).  
  
## <a name="example"></a>Пример  
 В следующем примере события используются для выполнения обратного отсчета от 10 до 0 секунд. Код иллюстрирует различные связанные с событиями методы, свойства и операторы. В том числе оператор `RaiseEvent`.  
  
 Класс, который вызывает событие, является источником события, а методы, обрабатывающие события, — обработчиками событий. Источник события может иметь несколько обработчиков для создаваемых им событий. Когда класс создает событие, это событие создается во всех классах, выбранных для обработки событий данного экземпляра объекта.  
  
 В примере также используется форма (`Form1`) с кнопкой (`Button1`) и текстовым полем (`TextBox1`). При нажатии кнопки в первом текстовом поле отображается обратный отсчет от 10 до 0 секунд. По истечении всего времени (10 секунд) в первом текстовом поле отображается надпись Done.  
  
 Код для `Form1` указывает начальное и конечное состояния формы. Он также содержит код, выполняемый при создании событий.  
  
 Чтобы использовать этот пример, откройте новый проект Windows Forms. Затем добавьте кнопку с именем `Button1` и текстовое поле с именем `TextBox1` в главную форму с именем `Form1`. Затем щелкните правой кнопкой мыши форму и нажмите кнопку **просмотреть код** , чтобы открыть редактор кода.  
  
 Добавьте переменную `WithEvents` в раздел объявлений класса `Form1`:  
  
 [!code-vb[VbVbalrEvents&#14;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/event-statement_2.vb)]  
  
 Добавьте следующий код в код для `Form1`. Замените все повторяющиеся процедуры, которые могут существовать, такие как `Form_Load` или `Button_Click`.  
  
 [!code-vb[VbVbalrEvents&#15;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/event-statement_3.vb)]  
  
 Нажмите клавишу F5 для запуска примера и нажмите кнопку с надписью **запустить**. Первое текстовое поле начинает обратный отсчет. По истечении всего времени (10 секунд) в первом текстовом поле отображается надпись Done.  
  
> [!NOTE]
>  Способ обработки событий методом `My.Application.DoEvents` отличается от обработки событий формой. Чтобы разрешить форме обрабатывать события напрямую, можно использовать многопоточность. Дополнительные сведения см. в разделе [потоки](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).  
  
## <a name="see-also"></a>См. также  
 [Оператор RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md)   
 [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)   
 [События](../../../visual-basic/programming-guide/language-features/events/index.md)   
 [Оператор AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [Оператор RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [Обрабатывает](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Практическое руководство: объявление пользовательских событий для экономии памяти](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)   
 [Практическое руководство: объявление пользовательских событий, чтобы избежать блокировки](../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)   
 [Общие](../../../visual-basic/language-reference/modifiers/shared.md)   
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
