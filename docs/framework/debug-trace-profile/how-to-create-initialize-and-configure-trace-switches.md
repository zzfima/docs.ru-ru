---
title: Практическое руководство. Создание, инициализация и настройка переключателей трассировки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- trace switches, configuring
- tracing [.NET Framework], trace switches
- switches, trace
- tracing [.NET Framework], enabling or disabling
- Web.config configuration file, trace switches
ms.assetid: 5a0e41bf-f99c-4692-8799-f89617f5bcf9
ms.openlocfilehash: 8bf3b974ff0ef9f719274ab684b3dce85295c917
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181829"
---
# <a name="how-to-create-initialize-and-configure-trace-switches"></a>Практическое руководство. Создание, инициализация и настройка переключателей трассировки
Переключатели трассировки позволяют включать, отключать и фильтровать выходные данные трассировки.  
  
<a name="create"></a>
## <a name="creating-and-initializing-a-trace-switch"></a>Создание и инициализация переключателей трассировки  
 Чтобы использовать переключатели трассировки, необходимо сначала создать их и разместить в коде. Существуют два предварительно определенных класса, с помощью которых можно создавать объекты переключателей: <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> и <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType>. Класс <xref:System.Diagnostics.BooleanSwitch> используется, когда требуется определить лишь факт отображения сообщений трассировки; если необходимо различать уровни трассировки, используется класс <xref:System.Diagnostics.TraceSwitch>. При использовании класса <xref:System.Diagnostics.TraceSwitch> можно определить собственные сообщения отладки и связать их с различными уровнями трассировки. Оба типа переключателей можно использовать как с трассировкой, так и с отладкой. По умолчанию класс <xref:System.Diagnostics.BooleanSwitch> отключен, а класс <xref:System.Diagnostics.TraceSwitch> имеет значение <xref:System.Diagnostics.TraceLevel.Off?displayProperty=nameWithType>. Переключатели трассировки можно создавать и помещать в любую часть кода, которая может их использовать.  
  
 Хотя допускается настройка уровней трассировки и других параметров конфигурации непосредственно в коде, для управления состоянием переключателей рекомендуется использовать файл конфигурации. Управление настройкой параметров в системе конфигурации обеспечивает большую гибкость — возможность включать и отключать различные переключатели и изменять уровни без перекомпиляции приложения.  
  
#### <a name="to-create-and-initialize-a-trace-switch"></a>Создание и инициализация переключателя трассировки  
  
1. Определите тип переключателя (<xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> или <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType>) и задайте его имя и описание.  
  
2. Настройте переключатель трассировки. Для получения дополнительной информации [см.](#configure)  
  
     Следующий код создает два переключателя, по одному для каждого типа.  
  
    ```vb  
    Dim dataSwitch As New BooleanSwitch("Data", "DataAccess module")  
    Dim generalSwitch As New TraceSwitch("General", "Entire application")  
    ```  
  
    ```csharp  
    System.Diagnostics.BooleanSwitch dataSwitch =
       new System.Diagnostics.BooleanSwitch("Data", "DataAccess module");  
    System.Diagnostics.TraceSwitch generalSwitch =
       new System.Diagnostics.TraceSwitch("General",
       "Entire application");  
    ```  
  
<a name="configure"></a>
## <a name="configuring-trace-switches"></a>Настройка переключателей трассировки  
 После распределения приложения можно по-прежнему включать или отключать вывод трассировки путем настройки в приложении переключателей трассировки. Настройка переключателя означает изменение его значения от внешнего источника после его инициализации. Можно изменить значения объектов переключателей с помощью файла конфигурации. Настройка переключателя трассировки выполняется для ее включения и отключения или для задания ее уровня, определяющего количество и тип сообщений, передаваемых в прослушиватели.  
  
 Настройка переключателей выполняется с помощью файла конфигурации. Для веб-приложения это файл Web.config, связанный с проектом. В приложении Windows этот файл называется (имя приложения). В развернутом приложении этот файл должен находиться в той же папке, что и исполняемая.  
  
 Когда приложение выполняет код, который создает экземпляр переключателя в первый раз, оно проверяет в файле конфигурации сведения уровня трассировки для именованного переключателя. Система трассировки проверяет файл конфигурации для каждого конкретного переключателя только один раз — при первом создании переключателя приложением.  
  
 В развернутом приложении вы включаете код трассировки путем повторной настройки объектов переключателей, когда приложение не запущено. Обычно это подразумевает включение и отключение объектов переключателей или изменение уровней трассировки, а затем перезапуск приложения.  
  
 При создании экземпляра переключателя вы также инициализируете его, указывая два аргумента: *displayName* и *description*. Аргумент *displayName* конструктора устанавливает свойство <xref:System.Diagnostics.Switch.DisplayName%2A?displayProperty=nameWithType> экземпляра класса <xref:System.Diagnostics.Switch>. Аргумент *displayName* — это имя, которое используется для настройки переключателя в файле .config, а аргумент *description* должен возвращать краткое описание переключателя и тип сообщений, которыми он управляет.  
  
 Помимо указания имени переключателя для настройки вы также должны указать значение для этого переключателя. Это значение представляет собой целое число. Для <xref:System.Diagnostics.BooleanSwitch> значение 0 соответствует значению **Off** (отключено), а любое ненулевое значение соответствует значению **On** (включено). Для <xref:System.Diagnostics.TraceSwitch> числа 0, 1, 2, 3 и 4 означают **Off** (отключено), **Error** (ошибка), **Warning** (предупреждение), **Info** (сведения) и **Verbose** (подробные сведения), соответственно. Любое число больше 4 интерпретируется как значение **Verbose** (подробно), а любое число меньше нуля — как значение **Off** (отключено).  
  
> [!NOTE]
> В .NET Framework версии 2.0 для указания значения переключателя можно использовать текст. Например, значение `true` для <xref:System.Diagnostics.BooleanSwitch> или текст, представляющий значение перечисления, такой как `Error`, для <xref:System.Diagnostics.TraceSwitch>. Строка `<add name="myTraceSwitch" value="Error" />` эквивалентна `<add name="myTraceSwitch" value="1" />`.  
  
 Чтобы конечные пользователи могли настраивать переключатели трассировки приложения, вы должны предоставить подробную документацию по переключателям в своем приложении. Необходимо подробно описать, какие переключатели чем управляют и как их включать и отключать. Вы также должны предоставить конечному пользователю файл конфигурации с соответствующей справкой в комментариях.  
  
#### <a name="to-configure-trace-switches"></a>Конфигурация коммутаторов трассировки  
  
1. Чтобы использовать переключатели трассировки, необходимо сначала создать их в коде, как описано в разделе [Создание и инициализация переключателя трассировки](#create).  
  
2. Если в проекте отсутствует файл конфигурации (app.config или Web.config), выберите **Добавить новый элемент** в меню **Проект**.  
  
    - **Visual Basic:** в диалоговом окне **Добавление нового элемента** выберите элемент **Файл конфигурации приложения**.  
  
         Файл конфигурации приложения создается и открывается. Это документ XML с корневым элементом `<configuration>.`  
  
    - **Visual C#:** в диалоговом окне **Добавление нового элемента** выберите элемент **XML-файл**. Назовите этот файл **app.config**. В редакторxML после декларации XML добавьте следующее XML:  
  
        ```xml  
        <configuration>  
        </configuration>  
        ```  
  
         При компиляции проекта файл app.config копируется в выходную папку проекта и получает новое имя: *имя_приложения*.exe.config.  
  
3. Добавьте соответствующий код XML для настройки переключателей между тегами `<configuration>` и `</configuration>`. В следующих примерах приведены переключатели **BooleanSwitch** (со свойством **DisplayName**, равным `DataMessageSwitch`) и **TraceSwitch** (со свойством **DisplayName**, равным `TraceLevelSwitch`).  
  
    ```xml  
    <system.diagnostics>  
       <switches>  
          <add name="DataMessagesSwitch" value="0" />  
          <add name="TraceLevelSwitch" value="0" />  
       </switches>  
    </system.diagnostics>  
    ```  
  
     В данной конфигурации оба переключателя отключены.  
  
4. Если необходимо включить переключатель **BooleanSwitch**, например `DataMessagesSwitch` в предыдущем примере, измените свойство **Value** на любое целое число, отличное от 0.  
  
5. Если необходимо включить переключатель **TraceSwitch**, например `TraceLevelSwitch` в предыдущем примере, измените свойство **Value** на подходящее значение уровня (от 1 до 4).  
  
6. Добавьте комментарии в файл конфигурации, чтобы конечный пользователь имел четкое представление, какие значения следует изменять для соответствующей настройки переключателей.  
  
     В следующем примере показано, как может выглядеть окончательный код, включая комментарии:  
  
    ```xml  
    <system.diagnostics>  
       <switches>  
          <!-- This switch controls data messages. In order to receive data   
             trace messages, change value="0" to value="1" -->  
          <add name="DataMessagesSwitch" value="0" />  
          <!-- This switch controls general messages. In order to   
             receive general trace messages change the value to the   
             appropriate level. "1" gives error messages, "2" gives errors   
             and warnings, "3" gives more detailed error information, and   
             "4" gives verbose trace information -->  
          <add name="TraceLevelSwitch" value="0" />  
       </switches>  
    </system.diagnostics>  
    ```  
  
## <a name="see-also"></a>См. также раздел

- [Трассировка и оборудование приложений](tracing-and-instrumenting-applications.md)
- [Практическое руководство. Добавление операторов трассировки в код приложения](how-to-add-trace-statements-to-application-code.md)
- [Переключатели трассировки](trace-switches.md)
- [Схема настроек трассировки и отпараги](../configure-apps/file-schema/trace-debug/index.md)
