---
title: Практическое руководство. Запись в журнал событий приложения
ms.date: 07/20/2015
helpviewer_keywords:
- Computer.EventLog element
- WriteEntry method [Visual Basic]
- My.Computer.EventLog element
- event logs, writing to
ms.assetid: cadbc8c1-87af-4746-934e-55b79a4f6e2b
ms.openlocfilehash: 511bb8fb16851872c1a16ae7627ed0fc6594337c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352048"
---
# <a name="how-to-write-to-an-application-event-log-visual-basic"></a>Практическое руководство. Запись в журнал событий приложения (Visual Basic)

Для записи информации о событиях, возникающих в приложении, можно использовать объекты `My.Application.Log` и `My.Log` . В этом примере показано, как настроить прослушиватель журнала событий, чтобы объект `My.Application.Log` записывал данные трассировки в журнал событий приложения.

Запись в журнал безопасности невозможна. Для записи в системный журнал необходимо быть членом учетной записи LocalSystem или "Администратор".

Для просмотра журнала событий можно использовать **обозреватель сервера** или **средство просмотра событий Windows**. Дополнительные сведения см. в разделе [События трассировки событий Windows в .NET Framework](../../../../framework/performance/etw-events.md).

## <a name="to-add-and-configure-the-event-log-listener"></a>Добавление и настройка прослушивателя журнала событий

1. Щелкните правой кнопкой мыши файл app.config в **обозревателе решений** и выберите команду **Открыть**.

    \- или -

    Если файл app.config отсутствует, выполните указанные ниже действия.

    1. В меню **Проект** выберите пункт **Добавить новый элемент**.

    2. В диалоговом окне **Добавление нового элемента** выберите элемент **Файл конфигурации приложения**.

    3. Нажмите кнопку **Добавить**.

2. Найдите раздел `<listeners>` в файле конфигурации приложения.

    Вы найдете раздел `<listeners>` в разделе `<source>` с атрибутом имени DefaultSource, вложенным в раздел `<system.diagnostics>` , который, в свою очередь, вложен в раздел `<configuration>` верхнего уровня.

3. Добавьте в этот раздел `<listeners>` следующий элемент:

    ```xml
    <add name="EventLog"/>
    ```

4. Найдите раздел `<sharedListeners>` в разделе `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.

5. Добавьте в этот раздел `<sharedListeners>` следующий элемент:

    ```xml
    <add name="EventLog"
        type="System.Diagnostics.EventLogTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="APPLICATION_NAME"/>
    ```

    Замените `APPLICATION_NAME` именем приложения.

    > [!NOTE]
    > Как правило, приложение записывает в журнал событий только ошибки. Сведения о фильтрации выходных данных журнала см. в разделе [Практическое руководство. Фильтрация выходных данных My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).

## <a name="to-write-event-information-to-the-event-log"></a>Запись информации о событии в журнал событий

Для записи информации в журнал событий используйте метод `My.Application.Log.WriteEntry` или `My.Application.Log.WriteException` . Дополнительные сведения см. в разделе [Практическое руководство. Запись сообщений в журнал](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) и [Практическое руководство. Исключения журналов](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).

После настройки прослушивателя журнала событий для сборки он получает все сообщения, которые записываются объектом `My.Application.Log` из этой сборки.

## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [Практическое руководство. Исплючения журналов](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
- [Пошаговое руководство: Определение места записи сведений для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
