---
title: "Оператор RaiseEvent | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
dev_langs:
- VB
helpviewer_keywords:
- raising events, RaiseEvent statement
- RaiseEvent statement
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
caps.latest.revision: 19
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
ms.openlocfilehash: 059b1347c4a35b896f5aa19cadb28fbceb8b25c9
ms.lasthandoff: 03/13/2017

---
# <a name="raiseevent-statement"></a>Оператор RaiseEvent
Вызывает событие, объявленное на уровне модуля в классе, форме или документе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a>Части  
 `eventname`  
 Обязательный. Имя события.  
  
 `argumentlist`  
 Необязательный. Разделенный запятыми список переменных, массивов и выражений. `argumentlist` Аргумент должен быть заключен в круглые скобки. Если не указано никаких аргументов, скобки следует опустить.  
  
## <a name="remarks"></a>Примечания  
 Обязательный `eventname` имя события, объявленного внутри модуля. Следует правилам именования переменных Visual Basic.  
  
 Если не была объявлена в модуле, в котором возникает событие, возникает ошибка. В следующем фрагменте кода демонстрируется объявление события и процедура, в которой возникает событие.  
  
 [!code-vb[VbVbalrEvents&#37;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]  
  
 Нельзя использовать `RaiseEvent` для создания событий, которые не объявлены явно в модуле. Например, наследуют все формы <xref:System.Windows.Forms.Control.Click>событие <xref:System.Windows.Forms.Form?displayProperty=fullName>, не может быть изменен с помощью `RaiseEvent` в производной форме.</xref:System.Windows.Forms.Form?displayProperty=fullName> </xref:System.Windows.Forms.Control.Click> При объявлении `Click` событий в модуле формы он скрывает формы собственный <xref:System.Windows.Forms.Control.Click>событий.</xref:System.Windows.Forms.Control.Click> Можно по-прежнему вызывать формы <xref:System.Windows.Forms.Control.Click>событие путем вызова <xref:System.Windows.Forms.Control.OnClick%2A>метод.</xref:System.Windows.Forms.Control.OnClick%2A> </xref:System.Windows.Forms.Control.Click>  
  
 По умолчанию события, определенные в Visual Basic вызывает обработчики событий в порядке установки подключений. Поскольку события могут содержать `ByRef` параметров, процесс, подключившийся позже, может получить параметры, измененные предыдущим обработчиком события. После выполнения обработчиков событий управление возвращается подпрограмме, вызвавшей событие.  
  
> [!NOTE]
>  Обычные события не должна возникать в конструкторе класса, в котором они объявлены. Хотя такие события не вызывают ошибки во время выполнения, они не будут перехватываться связанными обработчиками событий. Используйте `Shared` модификатор для создания совместно используемых событий, если необходимо вызвать событие из конструктора.  
  
> [!NOTE]
>  События по умолчанию можно изменить, определив пользовательское событие. Для пользовательских событий `RaiseEvent` инструкция вызывает событие `RaiseEvent` доступа. Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Пример  
 В следующем примере события используются для выполнения обратного отсчета от 10 до 0 секунд. Код иллюстрирует некоторые из связанных с событием методы, свойства и операторы, включая `RaiseEvent` инструкции.  
  
 Класс, который вызывает событие, является источником события, а методы, обрабатывающие события, — обработчиками событий. Источник события может иметь несколько обработчиков для создаваемых им событий. Когда класс создает событие, это событие создается во всех классах, выбранных для обработки событий данного экземпляра объекта.  
  
 В примере также используется форма (`Form1`) с кнопкой (`Button1`) и текстовым полем (`TextBox1`). При нажатии кнопки в первом текстовом поле отображается обратный отсчет от 10 до 0 секунд. По истечении всего времени (10 секунд) в первом текстовом поле отображается надпись Done.  
  
 Код для `Form1` указывает начальное и конечное состояния формы. Он также содержит код, выполняемый при создании событий.  
  
 Чтобы использовать этот пример, откройте новый проект приложения Windows, добавьте кнопку с именем `Button1` и текстовое поле с именем `TextBox1` в главную форму с именем `Form1`. Затем щелкните правой кнопкой мыши форму и нажмите кнопку **просмотреть код** , чтобы открыть редактор кода.  
  
 Добавить `WithEvents` переменных в раздел объявлений `Form1` класса.  
  
 [!code-vb[VbVbalrEvents&#14;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]  
  
## <a name="example"></a>Пример  
 Добавьте следующий код в код для `Form1`. Замените все дубликаты процедур, которые могут существовать, такие как `Form_Load`, или `Button_Click`.  
  
 [!code-vb[VbVbalrEvents&#15;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]  
  
 Нажмите клавишу F5 для запуска примера и нажмите кнопку с надписью **запустить**. Первое текстовое поле начинает обратный отсчет. По истечении всего времени (10 секунд) в первом текстовом поле отображается надпись Done.  
  
> [!NOTE]
>  `My.Application.DoEvents` Метод не обрабатывает события в точно так же, как формы. Чтобы разрешить форме непосредственно обрабатывать события, можно использовать многопоточность. Дополнительные сведения см. в разделе [потоки](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).  
  
## <a name="see-also"></a>См. также  
 [События](../../../visual-basic/programming-guide/language-features/events/index.md)   
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Оператор AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [Оператор RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [Обрабатывает](../../../visual-basic/language-reference/statements/handles-clause.md)
