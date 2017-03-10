---
title: "Пошаговое руководство. Фильтрация вывода My.Application.Log (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Log-объект, фильтрация вывода"
  - "Объект My.Application.Log, фильтрация вывода"
  - "журналы событий приложений, вывод фильтрации"
ms.assetid: 2c0a457a-38a4-49e1-934d-a51320b7b4ca
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Пошаговое руководство. Фильтрация вывода My.Application.Log (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

В этом пошаговом руководстве демонстрируется изменение фильтрации журнала по умолчанию `My.Application.Log` объекта, чтобы контролировать, какие данные передаются из `Log` объект в прослушиватели и управление информацией, записываемой прослушивателями. Можно изменить режим ведения журнала даже после создания приложения, поскольку сведения о конфигурации хранятся в файле конфигурации приложения.  
  
## <a name="getting-started"></a>Начало работы  
 Каждое сообщение, `My.Application.Log` запись имеет соответствующий уровень серьезности, использовать какие механизмы фильтрации для управления выводом в журнал. Этот пример приложения использует `My.Application.Log` методов для записи нескольких журналов сообщений с различными уровнями серьезности.  
  
#### <a name="to-build-the-sample-application"></a>Построение примера приложения  
  
1.  Откройте новую [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] проекта приложения Windows.  
  
2.  Добавьте кнопку с именем Button1 в форму Form1.  
  
3.  В <xref:System.Windows.Forms.Control.Click> обработчик событий для кнопки Button1, добавьте следующий код:  
  
     [!code-vb[VbVbcnMyApplicationLogFiltering#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/visualbasic/VbVbcnMyApplicationLogFiltering/Form1.vb#1)]  
  
4.  Запустите приложение в отладчике.  
  
5.  Нажмите клавишу **Button1**.  
  
     Приложение записывает следующие сведения в файл выходных данных и журналов отладки приложения.  
  
     `DefaultSource Information: 0 : In Button1_Click`  
  
     `DefaultSource Error: 2 : Error in the application.`  
  
6.  Закройте приложение.  
  
     Сведения о просмотре окна отладочного вывода приложения см. в разделе [окно вывода](/visual-studio/ide/reference/output-window). Сведения о расположении файла журнала приложения см. в разделе [Пошаговое руководство: определение информация](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).  
  
    > [!NOTE]
    >  По умолчанию приложение записывает вывод в файл журнала при закрытии приложения.  
  
     В примере выше, второй вызов <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A> метод и вызов <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A> метод выходные данные журнала, во время первого и последнего вызовы `WriteEntry` метода нет. Это, поскольку уровни серьезности `WriteEntry` и `WriteException` являются «Сведения» и «Ошибка», для которых разрешены `My.Application.Log` объекта фильтрации журнала по умолчанию. Однако события с уровнями серьезности «Начало» и «Stop» не выводятся в журнал.  
  
## <a name="filtering-for-all-myapplicationlog-listeners"></a>Фильтрация для всех прослушивателей My.Application.Log  
  `My.Application.Log` Объектов используют <xref:System.Diagnostics.SourceSwitch> с именем `DefaultSwitch` для управления передачей сообщений `WriteEntry` и `WriteException` методы прослушивателей журнала. Можно настроить `DefaultSwitch` в файле конфигурации приложения, установив его значение на одно из <xref:System.Diagnostics.SourceLevels> значений перечисления. По умолчанию его значение равно «Сведения».  
  
 В этой таблице показан уровень серьезности, необходимый для записи сообщения в прослушиватели для данного идентификатора `DefaultSwitch` параметр.  
  
|||  
|-|-|  
|Значение DefaultSwitch|Уровень серьезности сообщения, необходимый для вывода|  
|`Critical`|`Critical`|  
|`Error`|`Critical` или `Error`|  
|`Warning`|`Critical`, `Error` или `Warning`|  
|`Information`|`Critical`, `Error`, `Warning` или `Information`|  
|`Verbose`|`Critical`, `Error`, `Warning`, `Information` или `Verbose`|  
|`ActivityTracing`|`Start`, `Stop`, `Suspend`, `Resume` или `Transfer`|  
|`All`|Разрешены все сообщения.|  
|`Off`|Все сообщения блокируются.|  
  
> [!NOTE]
>   `WriteEntry` И `WriteException` каждый из методов имеет перегрузку, которая не содержит уровень серьезности. Неявный уровень серьезности для `WriteEntry` перегрузка является «Сведения» и неявный уровень серьезности для `WriteException` перегрузка является «Ошибка».  
  
 В следующей таблице показано в предыдущем примере показаны выходные данные журнала: по умолчанию `DefaultSwitch` параметр «Сведения», только второй вызов `WriteEntry` метод и вызов `WriteException` Выходные данные журнала создают метод.  
  
#### <a name="to-log-only-activity-tracing-events"></a>В журнал только события отслеживания действий  
  
1.  Щелкните правой кнопкой мыши файл app.config в **обозревателе решений** и выберите **Открыть**.  
  
     -или-  
  
     Если файл app.config отсутствует, выполните указанные ниже действия.  
  
    1.  В меню **Проект** выберите пункт **Добавить новый элемент**.  
  
    2.  В диалоговом окне **Добавление нового элемента** выберите элемент **Файл конфигурации приложения**.  
  
    3.  Нажмите кнопку **Добавить**.  
  
2.  Найдите `<switches>` раздела, в котором находится в `<system.diagnostics>` раздела, в котором находится на верхнем уровне `<configuration>` раздел.  
  
3.  Найдите элемент, добавляющий `DefaultSwitch` коллекцию переключателей. Он должен выглядеть аналогично этому элементу:  
  
     `<add name="DefaultSwitch" value="Information" />`  
  
4.  Измените значение `value` атрибут «ActivityTracing».  
  
5.  Содержимое файла app.config должно быть похоже на следующий код XML:  
  
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
  
6.  Запустите приложение в отладчике.  
  
7.  Нажмите клавишу **Button1**.  
  
     Приложение записывает следующие сведения в файл выходных данных и журналов отладки приложения.  
  
     `DefaultSource Start: 4 : Entering Button1_Click`  
  
     `DefaultSource Stop: 5 : Leaving Button1_Click`  
  
8.  Закройте приложение.  
  
9. Измените значение `value` атрибут «Сведения».  
  
    > [!NOTE]
    >   `DefaultSwitch` Переключение параметр определяет только `My.Application.Log`. Он не влияет на способ [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] <xref:System.Diagnostics.Trace?displayProperty=fullName> и <xref:System.Diagnostics.Debug?displayProperty=fullName> поведение классов.  
  
## <a name="individual-filtering-for-myapplicationlog-listeners"></a>Отдельные фильтрации для прослушивателей My.Application.Log  
 В предыдущем примере показано, как изменить фильтрацию для всех `My.Application.Log` Выходные данные. В этом примере демонстрируется способ фильтрации для отдельных прослушивателей журнала. По умолчанию приложение имеет два прослушивателя, которые выполняют запись в отладочный вывод приложения и файл журнала.  
  
 Файл конфигурации управляет поведением прослушивателей журнала, позволяя каждому из них иметь фильтр, аналогичный переключателю `My.Application.Log`. Прослушиватель журнала будет выводить сообщение только в том случае, если уровень серьезности сообщения допускается журнала `DefaultSwitch` и фильтром прослушивателя журнала.  
  
 В этом примере демонстрируется настройка фильтрации для нового прослушивателя отладки и добавление его `Log` объекта. Прослушиватели отладки по умолчанию должны быть удалены из `Log` объекта, чтобы обеспечить поступление сообщений отладки только из нового прослушивателя отладки.  
  
#### <a name="to-log-only-activity-tracing-events"></a>В журнал только события отслеживания действий  
  
1.  Щелкните правой кнопкой мыши файл app.config в **обозревателе решений** и выберите **Открыть**.  
  
     -или-  
  
     Если файл app.config отсутствует, выполните указанные ниже действия.  
  
    1.  В меню **Проект** выберите пункт **Добавить новый элемент**.  
  
    2.  В диалоговом окне **Добавление нового элемента** выберите элемент **Файл конфигурации приложения**.  
  
    3.  Нажмите кнопку **Добавить**.  
  
2.  Щелкните правой кнопкой мыши файл app.config в **обозревателе решений**. Выберите **Открыть**.  
  
3.  Найдите `<listeners>` раздела `<source>` статьи с `name` атрибутом «DefaultSource», который находится под `<sources>` раздел.  `<sources>` Раздел находится под `<system.diagnostics>` раздела верхнего уровня `<configuration>` раздел.  
  
4.  Этот элемент, чтобы добавить `<listeners>` раздел:  
  
    ```xml  
    <!-- Remove the default debug listener. -->  
    <remove name="Default"/>  
    <!-- Add a filterable debug listener. -->  
    <add name="NewDefault"/>  
    ```  
  
5.  Найдите раздел `<sharedListeners>` в разделе `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.  
  
6.  Добавьте в этот раздел `<sharedListeners>` следующий элемент:  
  
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
  
      <xref:System.Diagnostics.EventTypeFilter> Фильтр принимает один из <xref:System.Diagnostics.SourceLevels> значений перечисления, как его `initializeData` атрибута.  
  
7.  Содержимое файла app.config должно быть похоже на следующий код XML:  
  
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
  
8.  Запустите приложение в отладчике.  
  
9. Нажмите клавишу **Button1**.  
  
     Приложение записывает следующие сведения в файле журнала:  
  
     `Default Information: 0 : In Button1_Click`  
  
     `Default Error: 2 : Error in the application.`  
  
     Приложение записывает меньше информации в вывод отладки приложения из-за более строгой фильтрации.  
  
     `Default Error   2   Error`  
  
10. Закройте приложение.  
  
 Дополнительные сведения об изменении параметров журнала после развертывания см. в разделе [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).  
  
## <a name="see-also"></a>См. также  
 [Пошаговое руководство: Определение места записи информации для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)   
 [Пошаговое руководство: Изменение места записи информации для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)   
 [Пошаговое руководство: Создание пользовательских прослушивателей журнала](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md)   
 [Практическое руководство: запись сообщений в журнал](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)   
 [Переключатели трассировки](../Topic/Trace%20Switches.md)   
 [Запись сведений в приложение](../../../../visual-basic/developing-apps/programming/log-info/logging-information-from-the-application.md)