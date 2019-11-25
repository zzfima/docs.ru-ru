---
title: Запись сведений в журнал из приложения
ms.date: 07/20/2015
helpviewer_keywords:
- Log object
- My.Log object
- applications [Visual Basic], logging information from
- logging
- My.Application.Log object
- examples [Visual Basic], logging application information
ms.assetid: 8bf4f047-22d6-48d6-aec5-93b98ad5b8e8
ms.openlocfilehash: dace4bac3bf7529b8c50a492a092ad478f4d9e2d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353258"
---
# <a name="logging-information-from-the-application-visual-basic"></a>Запись сведений в журнал из приложения (Visual Basic)

Этот раздел содержит сведения о том, как регистрировать в журнале информацию из приложения с помощью объектов `My.Application.Log` или `My.Log` и как расширить возможности ведения журнала в приложении.  
  
 Объект `Log` предоставляет методы для записи информации в прослушиватели журнала приложения, а свойство `TraceSource` объекта `Log` предоставляет подробные сведения о конфигурации. Объект `Log` настраивается в файле конфигурации приложения.  
  
 Объект `My.Log` доступен только для приложений ASP.NET. Для клиентских приложений следует использовать объект `My.Application.Log`. Дополнительные сведения можно найти по адресу: <xref:Microsoft.VisualBasic.Logging.Log>.  
  
## <a name="tasks"></a>Задачи  
  
|Кому|См.|  
|--------|---------|  
|Запись информации о событиях в журналы приложения.|[Практическое руководство. Запись сообщений в журнал](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)|  
|Запись информации об исключениях в журналы приложения.|[Практическое руководство. Исплючения журналов](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)|  
|Запись данных трассировки в журналы приложения во время запуска и завершения работы приложения.|[Практическое руководство. Запись в журнал сообщений при запуске и завершении приложения](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-messages-when-the-application-starts-or-shuts-down.md)|  
|Настройка объекта `My.Application.Log` для записи информации в текстовый файл.|[Практическое руководство. Запись сведений о событиях в текстовый файл](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md)|  
|Настройка объекта `My.Application.Log` для записи информации в журнал событий.|[Практическое руководство. Запись в журнал событий приложения](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md)|  
|Изменение места, в которое объект `My.Application.Log` записывает информацию.|[Пошаговое руководство: Изменение места записи сведений для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)|  
|Выбор места, в которое объект `My.Application.Log` записывает информацию.|[Пошаговое руководство: Определение места записи сведений для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)|  
|Создание пользовательского прослушивателя журнала для `My.Application.Log`.|[Пошаговое руководство: Создание пользовательских прослушивателей журнала](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md)|  
|Фильтрация выходных данных журналов `My.Application.Log`.|[Пошаговое руководство: Фильтрация вывода My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)|  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [Устранение неполадок. Прослушиватели журнала](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)
