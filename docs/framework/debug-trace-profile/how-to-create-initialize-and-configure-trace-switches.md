---
title: "How to: Create, Initialize and Configure Trace Switches | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "trace switches, configuring"
  - "tracing [.NET Framework], trace switches"
  - "switches, trace"
  - "tracing [.NET Framework], enabling or disabling"
  - "Web.config configuration file, trace switches"
ms.assetid: 5a0e41bf-f99c-4692-8799-f89617f5bcf9
caps.latest.revision: 14
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# How to: Create, Initialize and Configure Trace Switches
Переключатели трассировки позволяют включать, отключать и фильтровать выходные данные трассировки.  
  
<a name="create"></a>   
## Создание и инициализация переключателя трассировки  
 Чтобы использовать переключатели трассировки, необходимо сначала создать их и разместить в коде. Существуют два предварительно определенных класса, с помощью которых можно создавать объекты переключателей: <xref:System.Diagnostics.BooleanSwitch?displayProperty=fullName> и <xref:System.Diagnostics.TraceSwitch?displayProperty=fullName>. Класс <xref:System.Diagnostics.BooleanSwitch> используется, когда требуется определить лишь факт отображения сообщений трассировки; если необходимо различать уровни трассировки, используется класс <xref:System.Diagnostics.TraceSwitch>. При использовании класса <xref:System.Diagnostics.TraceSwitch> можно определить собственные сообщения отладки и связать их с различными уровнями трассировки. Оба типа переключателей можно использовать как с трассировкой, так и с отладкой. По умолчанию класс <xref:System.Diagnostics.BooleanSwitch> отключен, а класс <xref:System.Diagnostics.TraceSwitch> имеет значение <xref:System.Diagnostics.TraceLevel?displayProperty=fullName>. Переключатели трассировки можно создавать и помещать в любую часть кода, которая может их использовать.  
  
 Хотя допускается настройка уровней трассировки и других параметров конфигурации непосредственно в коде, для управления состоянием переключателей рекомендуется использовать файл конфигурации. Управление настройкой параметров в системе конфигурации обеспечивает большую гибкость — возможность включать и отключать различные переключатели и изменять уровни без перекомпиляции приложения.  
  
#### Создание и инициализация переключателя трассировки  
  
1.  Определите тип переключателя \(<xref:System.Diagnostics.BooleanSwitch?displayProperty=fullName> или <xref:System.Diagnostics.TraceSwitch?displayProperty=fullName>\) и задайте его имя и описание.  
  
2.  Настройте переключатель трассировки. Дополнительные сведения см. в разделе [Настройка переключателей трассировки](#configure).  
  
     Следующий код создает два переключателя, по одному для каждого типа.  
  
    ```vb  
    Dim dataSwitch As New BooleanSwitch("Data", "DataAccess module") Dim generalSwitch As New TraceSwitch("General", "Entire application")  
  
    ```  
  
    ```csharp  
    System.Diagnostics.BooleanSwitch dataSwitch = new System.Diagnostics.BooleanSwitch("Data", "DataAccess module"); System.Diagnostics.TraceSwitch generalSwitch = new System.Diagnostics.TraceSwitch("General", "Entire application");  
  
    ```  
  
<a name="configure"></a>   
## Конфигурация коммутаторов трассировки  
 После распределения приложения можно по\-прежнему включать или отключать вывод трассировки путем настройки в приложении переключателей трассировки. Настройка переключателя означает изменение его значения от внешнего источника после его инициализации. Можно изменить значения объектов переключателей с помощью файла конфигурации. Настройка переключателя трассировки выполняется для ее включения и отключения или для задания ее уровня, определяющего количество и тип сообщений, передаваемых в прослушиватели.  
  
 Настройка переключателей выполняется с помощью файла конфигурации. Для веб\-приложения это файл Web.config, связанный с проектом. В приложении Windows этот файл называется \(имя приложения\).exe.config. В развернутом приложении этот файл должен находиться в той же папке, что и исполняемый файл.  
  
 Когда приложение выполняет код, который создает экземпляр переключателя в первый раз, оно проверяет в файле конфигурации сведения уровня трассировки для именованного переключателя. Система трассировки проверяет файл конфигурации для каждого конкретного переключателя только один раз — при первом создании переключателя приложением.  
  
 В развернутом приложении вы включаете код трассировки путем повторной настройки объектов переключателей, когда приложение не запущено. Обычно это подразумевает включение и отключение объектов переключателей или изменение уровней трассировки, а затем перезапуск приложения.  
  
 При создании экземпляра переключателя также выполняется его инициализация путем задания двух аргументов: *displayName* и *description*. Аргумент *DisplayName* конструктора задает свойство <xref:System.Diagnostics.Switch.DisplayName%2A?displayProperty=fullName> экземпляра класса <xref:System.Diagnostics.Switch>.*DisplayName* — это имя, которое используется для настройки переключателя в файле конфигурации, а аргумент *description* должен возвращать краткое описание переключателя, а также какими сообщениями он управляет.  
  
 Помимо указания имени переключателя для настройки вы также должны указать значение для этого переключателя. Это значение представляет собой целое число. Для <xref:System.Diagnostics.BooleanSwitch> значение 0 соответствует значению **Off** \(отключено\), а любое ненулевое значение соответствует значению **On** \(включено\). Для <xref:System.Diagnostics.TraceSwitch> числа 0,1,2,3 и 4 означают **Off** \(отключено\), **Error** \(ошибка\), **Warning** \(предупреждение\), **Info** \(сведения\) и **Verbose** \(подробно\) соответственно. Любое число больше 4 интерпретируется как значение **Verbose** \(подробно\), а любое число меньше нуля интерпретируется как значение **Off** \(отключено\).  
  
> [!NOTE]
>  В .NET Framework версии 2.0 для указания значения переключателя можно использовать текст. Например, значение `true` для <xref:System.Diagnostics.BooleanSwitch> или текст, представляющий значение перечисления, такой как `Error`, для <xref:System.Diagnostics.TraceSwitch>. Строка `<add name="myTraceSwitch" value="Error" />` эквивалентна `<add name="myTraceSwitch" value="1" />`.  
  
 Чтобы конечные пользователи могли настраивать переключатели трассировки приложения, вы должны предоставить подробную документацию по переключателям в своем приложении. Необходимо подробно описать, какие переключатели чем управляют и как их включать и отключать. Вы также должны предоставить конечному пользователю файл конфигурации с соответствующей справкой в комментариях.  
  
#### Конфигурация коммутаторов трассировки  
  
1.  Чтобы использовать коммутаторы трассировки, необходимо сначала создать их в коде, как описано в разделе [Создание и инициализация коммутатора трассировки](#create).  
  
2.  Если в проекте отсутствует файл конфигурации \(app.config или Web.config\), то в меню **Проект** выберите пункт **Добавить новый элемент**.  
  
    -   **Visual Basic:** в диалоговом окне **Добавление нового элемента** выберите элемент **Файл конфигурации приложения**.  
  
         Файл конфигурации приложения создается и открывается. Это документ XML с корневым элементом `<configuration>.`  
  
    -   **Visual C\#:** в диалоговом окне **Добавление нового элемента** выберите элемент **XML\-файл**. Дайте этому файлу имя **app.config**. В редакторе XML после объявления XML добавьте следующий XML\-код:  
  
        ```  
        <configuration> </configuration>  
        ```  
  
         При компиляции проекта файл app.config копируется в выходную папку проекта и получает новое имя *имя\_приложения*. exe.config.  
  
3.  После тега  `<configuration>` , но перед тегом  `</configuration>`  добавьте соответствующий XML для настройки переключателей. В следующих примерах демонстрируется **BooleanSwitch** со свойством **DisplayName**`DataMessageSwitch` и **TraceSwitch** со свойством **DisplayName**`TraceLevelSwitch`.  
  
    ```  
    <system.diagnostics> <switches> <add name="DataMessagesSwitch" value="0" /> <add name="TraceLevelSwitch" value="0" /> </switches> </system.diagnostics>  
    ```  
  
     В данной конфигурации оба переключателя отключены.  
  
4.  Если необходимо включить **BooleanSwitch**, такой как `DataMessagesSwitch`, показанный в предыдущем примере, измените свойство **Value** на любое целое число, отличное от 0.  
  
5.  Если необходимо включить **TraceSwitch**, такой как `TraceLevelSwitch`, показанный в предыдущем примере, измените свойство **Value** на соответствующий параметр уровня \(от 1 до 4\).  
  
6.  Добавьте комментарии в файл конфигурации, чтобы конечный пользователь имел четкое представление, какие значения следует изменять для соответствующей настройки переключателей.  
  
     В следующем примере показано, как может выглядеть окончательный код, включая комментарии:  
  
    ```  
    <system.diagnostics> <switches> <!-- This switch controls data messages. In order to receive data trace messages, change value="0" to value="1" --> <add name="DataMessagesSwitch" value="0" /> <!-- This switch controls general messages. In order to receive general trace messages change the value to the appropriate level. "1" gives error messages, "2" gives errors and warnings, "3" gives more detailed error information, and "4" gives verbose trace information --> <add name="TraceLevelSwitch" value="0" /> </switches> </system.diagnostics>  
    ```  
  
## См. также  
 [Tracing and Instrumenting Applications](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)   
 [How to: Add Trace Statements to Application Code](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)   
 [Trace Switches](../../../docs/framework/debug-trace-profile/trace-switches.md)   
 [Схема параметров трассировки и отладки](../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)