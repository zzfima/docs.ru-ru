---
title: "Практическое руководство. Запись в журнал сведений об исключениях в Visual Basic"
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
- exceptions, logging
- exceptions, tracking
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
caps.latest.revision: 19
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: adf2dc683a139d21f24379efc779d4510a2057eb
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-log-exceptions-in-visual-basic"></a>Практическое руководство. Запись в журнал сведений об исключениях в Visual Basic
Объекты `My.Application.Log` и `My.Log` можно использовать для записи в журнал сведений об исключениях, возникающих в приложении. Эти примеры демонстрируют применение метода `My.Application.Log.WriteException` для регистрации явно перехваченных исключений и исключений, которые не обрабатываются.  
  
 Для записи сведений в журнал используйте метод `My.Application.Log.WriteEntry`. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>.  
  
### <a name="to-log-a-handled-exception"></a>Запись обработанного исключения в журнал  
  
1.  Создайте метод, который будет генерировать сведения об исключении.  
  
     [!code-vb[VbVbalrMyApplicationLog#9](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_1.vb)]  
  
2.  Воспользуйтесь блоком `Try...Catch` для перехвата исключения.  
  
     [!code-vb[VbVbalrMyApplicationLog#6](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_2.vb)]  
  
3.  Поместите код, который может генерировать исключение, в блок `Try`.  
  
     Раскомментируйте строки `Dim` и `MsgBox`, чтобы вызвать исключение <xref:System.NullReferenceException>.  
  
     [!code-vb[VbVbalrMyApplicationLog#7](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_3.vb)]  
  
4.  В блоке `Catch` для записи сведений об исключении используйте метод `My.Application.Log.WriteException`.  
  
     [!code-vb[VbVbalrMyApplicationLog#8](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_4.vb)]  
  
     В следующем примере показан полный код для записи обработанного исключения в журнал.  
  
     [!code-vb[VbVbalrMyApplicationLog#10](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_5.vb)]  
  
### <a name="to-log-an-unhandled-exception"></a>Запись необработанного исключения в журнал  
  
1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.  
  
2.  Перейдите на вкладку **Приложение** .  
  
3.  Нажмите кнопку **Просмотреть события приложения** , чтобы открыть редактор кода.  
  
     Откроется файл ApplicationEvents.vb.  
  
4.  Откройте в редакторе кода файл ApplicationEvents.vb. В меню **Общие** выберите пункт **События MyApplication**.  
  
5.  В меню **Объявления** выберите пункт **UnhandledException**.  
  
     Приложение создает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> до запуска главного приложения.  
  
6.  Добавьте метод `My.Application.Log.WriteException` в обработчик событий `UnhandledException` .  
  
     [!code-vb[VbVbalrMyApplicationLog#4](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_6.vb)]  
  
     В следующем примере показан полный код для записи необработанного исключения в журнал.  
  
     [!code-vb[VbVbalrMyApplicationLog#5](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_7.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>   
 [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Практическое руководство. Запись сообщений в журнал](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)   
 [Пошаговое руководство. Определение места записи информации для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)   
 [Пошаговое руководство. Изменение места записи сведений для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)

