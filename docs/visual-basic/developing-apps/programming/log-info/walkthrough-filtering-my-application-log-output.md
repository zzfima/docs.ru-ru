---
title: Фильтрация вывода My.Application.Log (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Log object, filtering output
- My.Application.Log object, filtering output
- application event logs, output filtering
ms.assetid: 2c0a457a-38a4-49e1-934d-a51320b7b4ca
ms.openlocfilehash: 16cbbf9bf82e0c1e48eaacfcc9f07f718ed8de49
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524786"
---
# <a name="walkthrough-filtering-myapplicationlog-output-visual-basic"></a>Пошаговое руководство. Фильтрация вывода My.Application.Log (Visual Basic)

В этом пошаговом руководстве демонстрируется изменение фильтрации журнала по умолчанию для объекта `My.Application.Log`, чтобы контролировать, какие данные передаются из объекта `Log` в прослушиватели и какие данные записываются прослушивателями. Режим ведения журнала можно изменить даже после создания приложения, поскольку сведения о конфигурации хранятся в файле конфигурации приложения.

## <a name="getting-started"></a>Начало работы

Каждое сообщение, записываемое объектом `My.Application.Log`, имеет соответствующий уровень степени серьезности, используемый механизмами фильтрации для управления выходными данными журнала. В этом примере приложения используются методы `My.Application.Log` для записи нескольких сообщений журналов с различными уровнями степени серьезности.

#### <a name="to-build-the-sample-application"></a>Создание примера приложения

1. Откройте новый проект приложения Windows на Visual Basic.

2. Добавьте кнопку с именем Button1 в форму Form1.

3. В обработчик события <xref:System.Windows.Forms.Control.Click> добавьте следующий код для Button1:

     [!code-vb[VbVbcnMyApplicationLogFiltering#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyApplicationLogFiltering/VB/Form1.vb#1)]

4. Запустите приложение в отладчике.

5. Нажмите кнопку **Button1**.

     Приложение записывает следующие сведения в файл выходных данных отладки и файл журнала приложения.

     `DefaultSource Information: 0 : In Button1_Click`

     `DefaultSource Error: 2 : Error in the application.`

6. Закройте приложение.

     Сведения о просмотре окна вывода отладочных данных приложения см. в разделе [Окно вывода](/visualstudio/ide/reference/output-window). Дополнительные сведения о расположении файла журнала приложения см. в разделе [Пошаговое руководство. Определение места записи сведений для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).

    > [!NOTE]
    > По умолчанию приложение записывает выходные данные в файл журнала при закрытии приложения.

     В приведенном выше примере второй вызов метода <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A> и вызов метода <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A> приводят к получению данных журнала, а первый и последний вызовы метода `WriteEntry` — нет. Это связано с тем, что уровнями серьезности для `WriteEntry` и `WriteException` являются "Информация" и "Ошибка". Оба эти значения разрешены при фильтрации журнала по умолчанию для объекта `My.Application.Log`. Однако событиям с уровнями серьезности "Запуск" и "Остановка" запрещено создание выходных данных журнала.

## <a name="filtering-for-all-myapplicationlog-listeners"></a>Фильтрация всех прослушивателей My.Application.Log

Объект `My.Application.Log` использует <xref:System.Diagnostics.SourceSwitch> с именем `DefaultSwitch` для управления сообщениями, передаваемыми из методов `WriteEntry` и `WriteException` в прослушиватели журнала. `DefaultSwitch` можно настроить в файле конфигурации приложения, задав в качестве его значения одно из значений перечисления <xref:System.Diagnostics.SourceLevels>. По умолчанию используется значение "Информация".

В этой таблице показан уровень серьезности, необходимый журналу для записи сообщения в прослушиватели с конкретным параметром `DefaultSwitch`.

|Значение DefaultSwitch|Уровень серьезности сообщения, необходимый для вывода|
|---|---|
|`Critical`|`Critical`|
|`Error`|`Critical` или `Error`|
|`Warning`|`Critical`, `Error`или `Warning`|
|`Information`|`Critical`, `Error`, `Warning` или `Information`|
|`Verbose`|`Critical`, `Error`, `Warning`, `Information` или `Verbose`|
|`ActivityTracing`|`Start`, `Stop`, `Suspend`, `Resume` или `Transfer`|
|`All`|Все сообщения разрешены.|
|`Off`|Все сообщения блокируются.|

> [!NOTE]
> Каждый метод `WriteEntry` и `WriteException` имеет перегрузку, которая не указывает уровень серьезности. Неявным уровнем серьезности для перегрузки `WriteEntry` является "Информация", а неявным уровнем серьезности для перегрузки `WriteException` — "Ошибка".

В этой таблице приводятся выходные данные журнала из предыдущего примера: с параметром `DefaultSwitch` по умолчанию "Информация" только второй вызов метода `WriteEntry` и вызов метода `WriteException` формируют выходные данные журнала.

#### <a name="to-log-only-activity-tracing-events"></a>Запись в журнал только событий трассировки действий

1. Щелкните правой кнопкой мыши файл app.config в **обозревателе решений** и выберите команду **Открыть**.

     -или-

     Если файл app.config отсутствует, выполните указанные ниже действия.

    1. В меню **Проект** выберите пункт **Добавить новый элемент**.

    2. В диалоговом окне **Добавление нового элемента** выберите элемент **Файл конфигурации приложения**.

    3. Нажмите кнопку **Добавить**.

2. Найдите раздел `<switches>` в разделе `<system.diagnostics>` раздела `<configuration>` верхнего уровня.

3. Найдите элемент, добавляющий `DefaultSwitch` в коллекцию переключателей. Он должен выглядеть аналогично следующему элементу:

     `<add name="DefaultSwitch" value="Information" />`

4. Измените значение атрибута `value` данного свойства на "ActivityTracing".

5. Содержимое файла app.config должно быть похоже на следующий код XML:

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <system.diagnostics>
        <sources>
          <!-- This section configures My.Application.Log -->
          <source name="DefaultSource" switchName="DefaultSwitch">
            <listeners>
              <add name="FileLog"/>
            </listeners>
          </source>
        </sources>
        <switches>
          <add name="DefaultSwitch" value="ActivityTracing" />
        </switches>
        <sharedListeners>
          <add name="FileLog"
               type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
                     Microsoft.VisualBasic, Version=8.0.0.0,
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a,
                     processorArchitecture=MSIL"
               initializeData="FileLogWriter"/>
        </sharedListeners>
      </system.diagnostics>
    </configuration>
    ```

6. Запустите приложение в отладчике.

7. Нажмите кнопку **Button1**.

     Приложение записывает следующие сведения в файл выходных данных отладки и файл журнала приложения.

     `DefaultSource Start: 4 : Entering Button1_Click`

     `DefaultSource Stop: 5 : Leaving Button1_Click`

8. Закройте приложение.

9. Измените значение атрибута `value` снова на "Информация".

    > [!NOTE]
    > Параметр переключателя `DefaultSwitch` контролирует только `My.Application.Log`. На поведение классов <xref:System.Diagnostics.Trace?displayProperty=nameWithType> и <xref:System.Diagnostics.Debug?displayProperty=nameWithType> .NET Framework он не влияет.

## <a name="individual-filtering-for-myapplicationlog-listeners"></a>Отдельная фильтрация прослушивателей My.Application.Log

В предыдущем примере показано, как изменить фильтрацию для всех выходных данных `My.Application.Log`. В этом примере демонстрируется способ фильтрации отдельных прослушивателей журнала. По умолчанию приложение имеет два прослушивателя, которые выполняют запись в файл выходных данных отладки и файл журнала приложения.

Файл конфигурации управляет поведением прослушивателей журнала, разрешая каждому из них иметь фильтр, аналогичный переключателю `My.Application.Log`. Прослушиватель журнала будет выводить сообщение только в том случае, если уровень серьезности сообщения допускается фильтром `DefaultSwitch` журнала и фильтром прослушивателя журнала.

В этом примере демонстрируется настройка фильтрации для нового прослушивателя отладки и добавление его в объект `Log`. Прослушиватель отладки по умолчанию должен быть удален из объекта `Log`, чтобы сообщения отладки поступали только из нового прослушивателя отладки.

#### <a name="to-log-only-activity-tracing-events"></a>Запись в журнал только событий трассировки действий

1. Щелкните правой кнопкой мыши файл app.config в **обозревателе решений** и выберите команду **Открыть**.

     \-или-

     Если файл app.config отсутствует, выполните указанные ниже действия.

    1. В меню **Проект** выберите пункт **Добавить новый элемент**.

    2. В диалоговом окне **Добавление нового элемента** выберите элемент **Файл конфигурации приложения**.

    3. Нажмите кнопку **Добавить**.

2. Щелкните правой кнопкой мыши файл app.config в **обозревателе решений**. Выберите команду **Открыть**.

3. Найдите раздел `<listeners>` в разделе `<source>` с атрибутом `name`, равным DefaultSource, в разделе `<sources>`. Раздел `<sources>` находится в разделе `<system.diagnostics>` раздела `<configuration>` верхнего уровня.

4. Добавьте этот элемент в раздел `<listeners>`:

    ```xml
    <!-- Remove the default debug listener. -->
    <remove name="Default"/>
    <!-- Add a filterable debug listener. -->
    <add name="NewDefault"/>
    ```

5. Найдите раздел `<sharedListeners>` в разделе `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.

6. Добавьте в этот раздел `<sharedListeners>` следующий элемент:

    ```xml
    <add name="NewDefault"
         type="System.Diagnostics.DefaultTraceListener,
               System, Version=2.0.0.0, Culture=neutral,
               PublicKeyToken=b77a5c561934e089,
               processorArchitecture=MSIL">
        <filter type="System.Diagnostics.EventTypeFilter"
                initializeData="Error" />
    </add>
    ```

     Фильтр <xref:System.Diagnostics.EventTypeFilter> принимает одно из значений перечисления <xref:System.Diagnostics.SourceLevels> как атрибут `initializeData`.

7. Содержимое файла app.config должно быть похоже на следующий код XML:

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <system.diagnostics>
        <sources>
          <!-- This section configures My.Application.Log -->
          <source name="DefaultSource" switchName="DefaultSwitch">
            <listeners>
              <add name="FileLog"/>
              <!-- Remove the default debug listener. -->
              <remove name="Default"/>
              <!-- Add a filterable debug listener. -->
              <add name="NewDefault"/>
            </listeners>
          </source>
        </sources>
        <switches>
          <add name="DefaultSwitch" value="Information" />
        </switches>
        <sharedListeners>
          <add name="FileLog"
               type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
                     Microsoft.VisualBasic, Version=8.0.0.0,
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a,
                     processorArchitecture=MSIL"
               initializeData="FileLogWriter"/>
          <add name="NewDefault"
               type="System.Diagnostics.DefaultTraceListener,
                     System, Version=2.0.0.0, Culture=neutral,
                     PublicKeyToken=b77a5c561934e089,
                     processorArchitecture=MSIL">
            <filter type="System.Diagnostics.EventTypeFilter"
                    initializeData="Error" />
          </add>
        </sharedListeners>
      </system.diagnostics>
    </configuration>
    ```

8. Запустите приложение в отладчике.

9. Нажмите кнопку **Button1**.

     Приложение записывает следующие сведения в файл выходных данных приложения:

     `Default Information: 0 : In Button1_Click`

     `Default Error: 2 : Error in the application.`

     В связи с более ограничивающим фильтром приложение записывает меньше данных в выходные данные отладки приложения.

     `Default Error   2   Error`

10. Закройте приложение.

Дополнительные сведения об изменении параметров журнала после развертывания см. в разделе [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).

## <a name="see-also"></a>См. также

- [Пошаговое руководство: Определение места записи сведений для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
- [Пошаговое руководство: Изменение места записи сведений для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
- [Пошаговое руководство: Создание пользовательских прослушивателей журнала](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md)
- [Практическое руководство. Запись сообщений в журнал](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)
- [Переключатели трассировки](../../../../framework/debug-trace-profile/trace-switches.md)
- [Запись сведений в журнал из приложения](../../../../visual-basic/developing-apps/programming/log-info/index.md)
