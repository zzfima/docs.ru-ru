---
title: Практическое руководство. Запись в журнал сообщений при запуске и завершении приложения
ms.date: 07/20/2015
helpviewer_keywords:
- event logs, shutdown
- My.Application.Log object, logging
- Startup event [Visual Basic]
- event logs, startup
- Shutdown event [Visual Basic]
- My.Log object, logging
ms.assetid: 67624d05-cddf-48b7-8c36-5c99baa4c621
ms.openlocfilehash: 5a4ef3888ba8371d26204c3569b5fb9bae1f15f2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74352099"
---
# <a name="how-to-log-messages-when-the-application-starts-or-shuts-down-visual-basic"></a>Практическое руководство. Запись в журнал сообщений при запуске и завершении приложения (Visual Basic)

Объекты `My.Application.Log` и `My.Log` можно использовать для записи в журнал информации о событиях, происходящих в приложении. В этом примере показан способ использования метода `My.Application.Log.WriteEntry` с событиями `Startup` и `Shutdown` для записи сведений трассировки.  
  
### <a name="to-access-the-applications-event-handler-code"></a>Доступ к коду обработчика событий приложения  
  
1. Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.  
  
2. Перейдите на вкладку **Приложение** .  
  
3. Нажмите кнопку **Просмотреть события приложения** , чтобы открыть редактор кода.  
  
     Откроется файл ApplicationEvents.vb.  
  
### <a name="to-log-messages-when-the-application-starts"></a>Запись сообщений в журнал при запуске приложения  
  
1. Откройте в редакторе кода файл ApplicationEvents.vb. В меню **Общие** выберите пункт **События MyApplication**.  
  
2. В меню **Объявления** выберите пункт **Запуск**.  
  
     Приложение создает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> до запуска главного приложения.  
  
3. Добавьте метод `My.Application.Log.WriteEntry` в обработчик событий `Startup` .  
  
     [!code-vb[VbVbalrMyApplicationLog#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#1)]  
  
### <a name="to-log-messages-when-the-application-shuts-down"></a>Запись сообщений в журнал при завершении работы приложения  
  
1. Откройте в редакторе кода файл ApplicationEvents.vb. В меню **Общие** выберите пункт **События MyApplication**.  
  
2. В меню **Объявления** выберите пункт **Завершение работы**.  
  
     Приложение создает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> после запуска основного приложения, но до завершения его работы.  
  
3. Добавьте метод `My.Application.Log.WriteEntry` в обработчик событий `Shutdown` .  
  
     [!code-vb[VbVbalrMyApplicationLog#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#2)]  
  
## <a name="example"></a>Пример  

 Для доступа к событиям приложения в редакторе кода можно использовать **конструктор проектов** . Дополнительные сведения см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 [!code-vb[VbVbalrMyApplicationLog#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#3)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [Страница "Приложение" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
