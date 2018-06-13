---
title: Устранение неполадок, связанных с прослушивателями журнала (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- event logs, troubleshooting
- troubleshooting Visual Basic, event logs
- troubleshooting event logs
ms.assetid: ac6eb760-3d5d-461e-aedd-40599ee22e49
ms.openlocfilehash: 54c3ed0f607edf992fa3c40a8e6214252740587c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589048"
---
# <a name="troubleshooting-log-listeners-visual-basic"></a>Устранение неполадок, связанных с прослушивателями журнала (Visual Basic)
Объекты `My.Application.Log` и `My.Log` можно использовать для записи в журнал информации о событиях, происходящих в приложении.  
  
 Чтобы определить, какие прослушиватели журналов получают эти сообщения, см. раздел [Пошаговое руководство. Определение места записи информации для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).  
  
 Объект `Log` может использовать фильтрацию журнала для ограничения объема данных, регистрируемых в журнале. Если фильтры настроены неправильно, журналы могут содержать неверные данные. Дополнительные сведения см. в разделе [Пошаговое руководство. Фильтрация вывода My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).  
  
 Однако если журнал настроен неправильно, необходима дополнительная информация о его текущей конфигурации. Эту информацию можно получить с помощью расширенного свойства журнала `TraceSource`.  
  
### <a name="to-determine-the-log-listeners-for-the-log-object-in-code"></a>Определение прослушивателей журнала для объекта Log в коде  
  
1.  Импортируйте пространство имен <xref:System.Diagnostics> в начало файла кода. Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
     [!code-vb[VbVbalrMyApplicationLog#13](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_1.vb)]  
  
2.  Создайте функцию, которая возвращает строку, состоящую из информации о каждом из прослушивателей журнала.  
  
     [!code-vb[VbVbalrMyApplicationLog#14](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_2.vb)]  
  
3.  Передайте коллекцию прослушивателей журнала трассировки в функцию `GetListeners` и отобразите возвращаемое значение.  
  
     [!code-vb[VbVbalrMyApplicationLog#19](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_3.vb)]  
  
     Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [Пошаговое руководство. Определение места записи сведений для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
