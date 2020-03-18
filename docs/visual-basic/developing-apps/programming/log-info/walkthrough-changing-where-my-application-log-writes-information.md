---
title: Изменение места записи сведений для My.Application.Log
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, walkthroughs
- event logs, changing output location
ms.assetid: ecc74f95-743c-450d-93f6-09a30db0fe4a
ms.openlocfilehash: bdee0a91360580b156c1734ef4c82139b18ce2b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74336737"
---
# <a name="walkthrough-changing-where-myapplicationlog-writes-information-visual-basic"></a><span data-ttu-id="3acd8-102">Пошаговое руководство. Изменение места записи информации для My.Application.Log (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3acd8-102">Walkthrough: Changing Where My.Application.Log Writes Information (Visual Basic)</span></span>

<span data-ttu-id="3acd8-103">Объекты `My.Application.Log` и `My.Log` можно использовать для записи в журнал информации о событиях, происходящих в приложении.</span><span class="sxs-lookup"><span data-stu-id="3acd8-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span> <span data-ttu-id="3acd8-104">В этом пошаговом руководстве показано, как переопределить параметры по умолчанию и настроить объект `Log` на запись в другие прослушиватели журналов.</span><span class="sxs-lookup"><span data-stu-id="3acd8-104">This walkthrough shows how to override the default settings and cause the `Log` object to write to other log listeners.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3acd8-105">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="3acd8-105">Prerequisites</span></span>

<span data-ttu-id="3acd8-106">Объект `Log` может записывать информацию в несколько прослушивателей журналов.</span><span class="sxs-lookup"><span data-stu-id="3acd8-106">The `Log` object can write information to several log listeners.</span></span> <span data-ttu-id="3acd8-107">Перед изменением конфигурации необходимо определить текущую конфигурацию прослушивателей журналов.</span><span class="sxs-lookup"><span data-stu-id="3acd8-107">You need to determine the current configuration of the log listeners before changing the configurations.</span></span> <span data-ttu-id="3acd8-108">Для получения дополнительной информации см. [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="3acd8-108">For more information, see [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span></span>

<span data-ttu-id="3acd8-109">Также см. разделы [Практическое руководство. Запись сведений о событиях в текстовый файл](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md) и [Практическое руководство. Запись в журнал событий приложения](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md).</span><span class="sxs-lookup"><span data-stu-id="3acd8-109">You may want to review [How to: Write Event Information to a Text File](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md) or [How to: Write to an Application Event Log](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md).</span></span>

### <a name="to-add-listeners"></a><span data-ttu-id="3acd8-110">Добавление прослушивателей</span><span class="sxs-lookup"><span data-stu-id="3acd8-110">To add listeners</span></span>

1. <span data-ttu-id="3acd8-111">Щелкните правой кнопкой мыши файл app.config в **обозревателе решений** и выберите команду **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="3acd8-111">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>

     <span data-ttu-id="3acd8-112">\- или -</span><span class="sxs-lookup"><span data-stu-id="3acd8-112">\- or -</span></span>

     <span data-ttu-id="3acd8-113">Если файл app.config отсутствует, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3acd8-113">If there is no app.config file:</span></span>

    1. <span data-ttu-id="3acd8-114">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="3acd8-114">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="3acd8-115">В диалоговом окне **Добавление нового элемента** выберите элемент **Файл конфигурации приложения**.</span><span class="sxs-lookup"><span data-stu-id="3acd8-115">From the **Add New Item** dialog box, select **Application Configuration File**.</span></span>

    3. <span data-ttu-id="3acd8-116">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3acd8-116">Click **Add**.</span></span>

2. <span data-ttu-id="3acd8-117">Найдите раздел `<listeners>` в разделе `<source>` с атрибутом `name` , равным DefaultSource, в разделе `<sources>` .</span><span class="sxs-lookup"><span data-stu-id="3acd8-117">Locate the `<listeners>` section, under the `<source>` section with the `name` attribute "DefaultSource", in the `<sources>` section.</span></span> <span data-ttu-id="3acd8-118">Раздел `<sources>` находится в разделе `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="3acd8-118">The `<sources>` section is in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

3. <span data-ttu-id="3acd8-119">Добавьте в этот раздел `<listeners>` следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="3acd8-119">Add these elements to that `<listeners>` section.</span></span>

    ```xml
    <!-- Uncomment to connect the application file log. -->
    <!-- <add name="FileLog" /> -->
    <!-- Uncomment to connect the event log. -->
    <!-- <add name="EventLog" /> -->
    <!-- Uncomment to connect the event log. -->
    <!-- <add name="Delimited" /> -->
    <!-- Uncomment to connect the XML log. -->
    <!-- <add name="XmlWriter" /> -->
    <!-- Uncomment to connect the console log. -->
    <!-- <add name="Console" /> -->
    ```

4. <span data-ttu-id="3acd8-120">Раскомментируйте прослушиватели журналов, которые должны получать сообщения `Log` .</span><span class="sxs-lookup"><span data-stu-id="3acd8-120">Uncomment the log listeners that you want to receive `Log` messages.</span></span>

5. <span data-ttu-id="3acd8-121">Найдите раздел `<sharedListeners>` в разделе `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="3acd8-121">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

6. <span data-ttu-id="3acd8-122">Добавьте в этот раздел `<sharedListeners>` следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="3acd8-122">Add these elements to that `<sharedListeners>` section.</span></span>

    ```xml
    <add name="FileLog"
         type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
               Microsoft.VisualBasic, Version=8.0.0.0,
               Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"
         initializeData="FileLogWriter" />
    <add name="EventLog"
         type="System.Diagnostics.EventLogTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="sample application"/>
    <add name="Delimited"
         type="System.Diagnostics.DelimitedListTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="c:\temp\sampleDelimitedFile.txt"
         traceOutputOptions="DateTime" />
    <add name="XmlWriter"
         type="System.Diagnostics.XmlWriterTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="c:\temp\sampleLogFile.xml" />
    <add name="Console"
         type="System.Diagnostics.ConsoleTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="true" />
    ```

7. <span data-ttu-id="3acd8-123">Содержимое файла app.config должно быть похоже на следующий код XML:</span><span class="sxs-lookup"><span data-stu-id="3acd8-123">The content of the app.config file should be similar to the following XML:</span></span>

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <system.diagnostics>
        <sources>
          <!-- This section configures My.Application.Log -->
          <source name="DefaultSource" switchName="DefaultSwitch">
            <listeners>
              <add name="FileLog"/>
              <!-- Uncomment to connect the application file log. -->
              <!-- <add name="FileLog" /> -->
              <!-- Uncomment to connect the event log. -->
              <!-- <add name="EventLog" /> -->
              <!-- Uncomment to connect the event log. -->
              <!-- <add name="Delimited" /> -->
              <!-- Uncomment to connect the XML log. -->
              <!-- <add name="XmlWriter" /> -->
              <!-- Uncomment to connect the console log. -->
              <!-- <add name="Console" /> -->
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
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"
               initializeData="FileLogWriter" />
          <add name="EventLog"
               type="System.Diagnostics.EventLogTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="sample application"/>
          <add name="Delimited"
               type="System.Diagnostics.DelimitedListTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="c:\temp\sampleDelimitedFile.txt"
               traceOutputOptions="DateTime" />
          <add name="XmlWriter"
               type="System.Diagnostics.XmlWriterTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="c:\temp\sampleLogFile.xml" />
          <add name="Console"
               type="System.Diagnostics.ConsoleTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="true" />
        </sharedListeners>
      </system.diagnostics>
    </configuration>
    ```

### <a name="to-reconfigure-a-listener"></a><span data-ttu-id="3acd8-124">Перенастройка прослушивателя</span><span class="sxs-lookup"><span data-stu-id="3acd8-124">To reconfigure a listener</span></span>

1. <span data-ttu-id="3acd8-125">Найдите элемент `<add>` прослушивателя из раздела `<sharedListeners>` .</span><span class="sxs-lookup"><span data-stu-id="3acd8-125">Locate the listener's `<add>` element from the `<sharedListeners>` section.</span></span>

2. <span data-ttu-id="3acd8-126">Атрибут `type` содержит имя типа прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="3acd8-126">The `type` attribute gives the name of the listener type.</span></span> <span data-ttu-id="3acd8-127">Этот тип должен наследоваться от класса <xref:System.Diagnostics.TraceListener> .</span><span class="sxs-lookup"><span data-stu-id="3acd8-127">This type must inherit from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="3acd8-128">Используйте строгое имя типа, чтобы гарантировать, что используется верный тип.</span><span class="sxs-lookup"><span data-stu-id="3acd8-128">Use the strongly named type name to ensure that the right type is used.</span></span> <span data-ttu-id="3acd8-129">Дополнительные сведения см. в разделе "Создание ссылки на строго именованный тип" ниже.</span><span class="sxs-lookup"><span data-stu-id="3acd8-129">For more information, see the "To reference a strongly named type" section below.</span></span>

     <span data-ttu-id="3acd8-130">Вот некоторые типы, которые можно использовать:</span><span class="sxs-lookup"><span data-stu-id="3acd8-130">Some types that you can use are:</span></span>

    - <span data-ttu-id="3acd8-131">прослушиватель <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> , ведущий запись в журнал файлов;</span><span class="sxs-lookup"><span data-stu-id="3acd8-131">A <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> listener, which writes to a file log.</span></span>

    - <span data-ttu-id="3acd8-132">прослушиватель <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> , записывающий информацию в журнал событий компьютера, заданный параметром `initializeData` ;</span><span class="sxs-lookup"><span data-stu-id="3acd8-132">A <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> listener, which writes information to the computer event log specified by the `initializeData` parameter.</span></span>

    - <span data-ttu-id="3acd8-133">прослушиватели <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> и <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> , ведущие запись в файл, указанный в параметре `initializeData` ;</span><span class="sxs-lookup"><span data-stu-id="3acd8-133">The <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> and <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> listeners, which write to the file specified in the `initializeData` parameter.</span></span>

    - <span data-ttu-id="3acd8-134">прослушиватель <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> , ведущий запись в консоль командной строки.</span><span class="sxs-lookup"><span data-stu-id="3acd8-134">A <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> listener, which writes to the command-line console.</span></span>

     <span data-ttu-id="3acd8-135">Сведения о том, куда записывают информацию другие типы прослушивателей журналов, приведены в документации по этим типам.</span><span class="sxs-lookup"><span data-stu-id="3acd8-135">For information about where other types of log listeners write information, consult that type's documentation.</span></span>

3. <span data-ttu-id="3acd8-136">Когда приложение создает объект прослушивателя журнала, оно передает атрибут `initializeData` в качестве параметра конструктора.</span><span class="sxs-lookup"><span data-stu-id="3acd8-136">When the application creates the log-listener object, it passes the `initializeData` attribute as the constructor parameter.</span></span> <span data-ttu-id="3acd8-137">Значение атрибута `initializeData` зависит от прослушивателя трассировки.</span><span class="sxs-lookup"><span data-stu-id="3acd8-137">The meaning of the `initializeData` attribute depends on the trace listener.</span></span>

4. <span data-ttu-id="3acd8-138">После создания прослушивателя журнала приложение задает его свойства.</span><span class="sxs-lookup"><span data-stu-id="3acd8-138">After creating the log listener, the application sets the listener's properties.</span></span> <span data-ttu-id="3acd8-139">Эти свойства определяются другими атрибутами в элементе `<add>` .</span><span class="sxs-lookup"><span data-stu-id="3acd8-139">These properties are defined by the other attributes in the `<add>` element.</span></span> <span data-ttu-id="3acd8-140">Дополнительные сведения о свойствах конкретного прослушивателя см. в документации к соответствующему типу прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="3acd8-140">For more information on the properties for a particular listener, see the documentation for that listener's type.</span></span>

### <a name="to-reference-a-strongly-named-type"></a><span data-ttu-id="3acd8-141">Создание ссылки на строго именованный тип</span><span class="sxs-lookup"><span data-stu-id="3acd8-141">To reference a strongly named type</span></span>

1. <span data-ttu-id="3acd8-142">Чтобы гарантировать, что для прослушивателя журнала используется правильный тип, убедитесь в том, что используется полное имя типа и строгое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="3acd8-142">To ensure that the right type is used for your log listener, make sure to use the fully qualified type name and the strongly named assembly name.</span></span> <span data-ttu-id="3acd8-143">Синтаксис строго именованного типа выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3acd8-143">The syntax of a strongly named type is as follows:</span></span>

     <span data-ttu-id="3acd8-144">\<*имя типа*>, \<*имя сборки*>, \<*номер версии*>, \<*язык и региональные параметры*>, \<*строгое имя*></span><span class="sxs-lookup"><span data-stu-id="3acd8-144">\<*type name*>, \<*assembly name*>, \<*version number*>, \<*culture*>, \<*strong name*></span></span>

2. <span data-ttu-id="3acd8-145">В этом примере кода показано, как определить строгое имя для типа с полным именем System.Diagnostics.FileLogTraceListener.</span><span class="sxs-lookup"><span data-stu-id="3acd8-145">This code example shows how to determine the strongly named type name for a fully qualified type—"System.Diagnostics.FileLogTraceListener" in this case.</span></span>

     [!code-vb[VbVbalrMyApplicationLog#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#15)]

     <span data-ttu-id="3acd8-146">Это выходные данные, и они могут использоваться для уникальной ссылки на строго именованный тип, как показано выше в процедуре "Добавление прослушивателей".</span><span class="sxs-lookup"><span data-stu-id="3acd8-146">This is the output, and it can be used to uniquely reference a strongly named type, as in the "To add listeners" procedure above.</span></span>

     `Microsoft.VisualBasic.Logging.FileLogTraceListener, Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`

## <a name="see-also"></a><span data-ttu-id="3acd8-147">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3acd8-147">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType>
- <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>
- [<span data-ttu-id="3acd8-148">Практическое руководство. Запись сведений о событиях в текстовый файл</span><span class="sxs-lookup"><span data-stu-id="3acd8-148">How to: Write Event Information to a Text File</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md)
- [<span data-ttu-id="3acd8-149">Практическое руководство. Запись в журнал событий приложения</span><span class="sxs-lookup"><span data-stu-id="3acd8-149">How to: Write to an Application Event Log</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md)
