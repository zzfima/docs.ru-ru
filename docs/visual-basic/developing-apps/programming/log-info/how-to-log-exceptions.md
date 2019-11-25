---
title: Практическое руководство. Запись исключений в журнал
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, logging
- exceptions, tracking
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
ms.openlocfilehash: fe6949d727fae0c230ce7421b32fdaf2a498edbc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352090"
---
# <a name="how-to-log-exceptions-in-visual-basic"></a>Практическое руководство. Запись в журнал сведений об исключениях в Visual Basic

Объекты `My.Application.Log` и `My.Log` можно использовать для записи в журнал сведений об исключениях, возникающих в приложении. Эти примеры демонстрируют применение метода `My.Application.Log.WriteException` для регистрации явно перехваченных исключений и исключений, которые не обрабатываются.  
  
 Для записи сведений в журнал используйте метод `My.Application.Log.WriteEntry`. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>.  
  
### <a name="to-log-a-handled-exception"></a>Запись обработанного исключения в журнал  
  
1. Создайте метод, который будет генерировать сведения об исключении.  
  
     [!code-vb[VbVbalrMyApplicationLog#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#9)]  
  
2. Воспользуйтесь блоком `Try...Catch` для перехвата исключения.  
  
     [!code-vb[VbVbalrMyApplicationLog#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#6)]  
  
3. Поместите код, который может генерировать исключение, в блок `Try`.  
  
     Раскомментируйте строки `Dim` и `MsgBox`, чтобы вызвать исключение <xref:System.NullReferenceException>.  
  
     [!code-vb[VbVbalrMyApplicationLog#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#7)]  
  
4. В блоке `Catch` для записи сведений об исключении используйте метод `My.Application.Log.WriteException`.  
  
     [!code-vb[VbVbalrMyApplicationLog#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#8)]  
  
     В следующем примере показан полный код для записи обработанного исключения в журнал.  
  
     [!code-vb[VbVbalrMyApplicationLog#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#10)]  
  
### <a name="to-log-an-unhandled-exception"></a>Запись необработанного исключения в журнал  
  
1. Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.  
  
2. Перейдите на вкладку **Приложение** .  
  
3. Нажмите кнопку **Просмотреть события приложения** , чтобы открыть редактор кода.  
  
     Откроется файл ApplicationEvents.vb.  
  
4. Откройте в редакторе кода файл ApplicationEvents.vb. В меню **Общие** выберите пункт **События MyApplication**.  
  
5. В меню **Объявления** выберите пункт **UnhandledException**.  
  
     Приложение создает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> до запуска главного приложения.  
  
6. Добавьте метод `My.Application.Log.WriteException` в обработчик событий `UnhandledException` .  
  
     [!code-vb[VbVbalrMyApplicationLog#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#4)]  
  
     В следующем примере показан полный код для записи необработанного исключения в журнал.  
  
     [!code-vb[VbVbalrMyApplicationLog#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#5)]  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [Практическое руководство. Запись сообщений в журнал](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)
- [Пошаговое руководство: Определение места записи сведений для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
- [Пошаговое руководство: Изменение места записи сведений для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
