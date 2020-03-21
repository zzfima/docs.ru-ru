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
# <a name="how-to-create-initialize-and-configure-trace-switches"></a><span data-ttu-id="00708-102">Практическое руководство. Создание, инициализация и настройка переключателей трассировки</span><span class="sxs-lookup"><span data-stu-id="00708-102">How to: Create, Initialize and Configure Trace Switches</span></span>
<span data-ttu-id="00708-103">Переключатели трассировки позволяют включать, отключать и фильтровать выходные данные трассировки.</span><span class="sxs-lookup"><span data-stu-id="00708-103">Trace switches enable you to enable, disable, and filter tracing output.</span></span>  
  
<a name="create"></a>
## <a name="creating-and-initializing-a-trace-switch"></a><span data-ttu-id="00708-104">Создание и инициализация переключателей трассировки</span><span class="sxs-lookup"><span data-stu-id="00708-104">Creating and initializing a trace switch</span></span>  
 <span data-ttu-id="00708-105">Чтобы использовать переключатели трассировки, необходимо сначала создать их и разместить в коде.</span><span class="sxs-lookup"><span data-stu-id="00708-105">In order to use trace switches, you must first create them and place them in your code.</span></span> <span data-ttu-id="00708-106">Существуют два предварительно определенных класса, с помощью которых можно создавать объекты переключателей: <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> и <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="00708-106">There are two predefined classes from which you can create switch objects: the <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> class and the <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="00708-107">Класс <xref:System.Diagnostics.BooleanSwitch> используется, когда требуется определить лишь факт отображения сообщений трассировки; если необходимо различать уровни трассировки, используется класс <xref:System.Diagnostics.TraceSwitch>.</span><span class="sxs-lookup"><span data-stu-id="00708-107">You would use <xref:System.Diagnostics.BooleanSwitch> if you care only about whether or not a tracing message appears; you would use <xref:System.Diagnostics.TraceSwitch> if you want to discriminate between levels of tracing.</span></span> <span data-ttu-id="00708-108">При использовании класса <xref:System.Diagnostics.TraceSwitch> можно определить собственные сообщения отладки и связать их с различными уровнями трассировки.</span><span class="sxs-lookup"><span data-stu-id="00708-108">If you use a <xref:System.Diagnostics.TraceSwitch>, you can define your own debugging messages and associate them with different trace levels.</span></span> <span data-ttu-id="00708-109">Оба типа переключателей можно использовать как с трассировкой, так и с отладкой.</span><span class="sxs-lookup"><span data-stu-id="00708-109">You can use both types of switches with either tracing or debugging.</span></span> <span data-ttu-id="00708-110">По умолчанию класс <xref:System.Diagnostics.BooleanSwitch> отключен, а класс <xref:System.Diagnostics.TraceSwitch> имеет значение <xref:System.Diagnostics.TraceLevel.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="00708-110">By default, a <xref:System.Diagnostics.BooleanSwitch> is disabled and a <xref:System.Diagnostics.TraceSwitch> is set to level <xref:System.Diagnostics.TraceLevel.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="00708-111">Переключатели трассировки можно создавать и помещать в любую часть кода, которая может их использовать.</span><span class="sxs-lookup"><span data-stu-id="00708-111">Trace switches can be created and placed in any part of your code that might use them.</span></span>  
  
 <span data-ttu-id="00708-112">Хотя допускается настройка уровней трассировки и других параметров конфигурации непосредственно в коде, для управления состоянием переключателей рекомендуется использовать файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="00708-112">Although you can set trace levels and other configuration options in code, we recommend that you use the configuration file to manage the state of your switches.</span></span> <span data-ttu-id="00708-113">Управление настройкой параметров в системе конфигурации обеспечивает большую гибкость — возможность включать и отключать различные переключатели и изменять уровни без перекомпиляции приложения.</span><span class="sxs-lookup"><span data-stu-id="00708-113">This is because managing the configuration of your switches in the configuration system gives you greater flexibility — you can turn on and off various switches and change levels without recompiling your application.</span></span>  
  
#### <a name="to-create-and-initialize-a-trace-switch"></a><span data-ttu-id="00708-114">Создание и инициализация переключателя трассировки</span><span class="sxs-lookup"><span data-stu-id="00708-114">To create and initialize a trace switch</span></span>  
  
1. <span data-ttu-id="00708-115">Определите тип переключателя (<xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> или <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType>) и задайте его имя и описание.</span><span class="sxs-lookup"><span data-stu-id="00708-115">Define a switch as either type <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> or type <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType> and set the name and description of the switch.</span></span>  
  
2. <span data-ttu-id="00708-116">Настройте переключатель трассировки.</span><span class="sxs-lookup"><span data-stu-id="00708-116">Configure your trace switch.</span></span> <span data-ttu-id="00708-117">Для получения дополнительной информации [см.](#configure)</span><span class="sxs-lookup"><span data-stu-id="00708-117">For more information, see [Configuring trace switches](#configure).</span></span>  
  
     <span data-ttu-id="00708-118">Следующий код создает два переключателя, по одному для каждого типа.</span><span class="sxs-lookup"><span data-stu-id="00708-118">The following code creates two switches, one of each type:</span></span>  
  
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
## <a name="configuring-trace-switches"></a><span data-ttu-id="00708-119">Настройка переключателей трассировки</span><span class="sxs-lookup"><span data-stu-id="00708-119">Configuring trace switches</span></span>  
 <span data-ttu-id="00708-120">После распределения приложения можно по-прежнему включать или отключать вывод трассировки путем настройки в приложении переключателей трассировки.</span><span class="sxs-lookup"><span data-stu-id="00708-120">After your application has been distributed, you can still enable or disable trace output by configuring the trace switches in your application.</span></span> <span data-ttu-id="00708-121">Настройка переключателя означает изменение его значения от внешнего источника после его инициализации.</span><span class="sxs-lookup"><span data-stu-id="00708-121">Configuring a switch means changing its value from an external source after it has been initialized.</span></span> <span data-ttu-id="00708-122">Можно изменить значения объектов переключателей с помощью файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="00708-122">You can change the values of the switch objects using the configuration file.</span></span> <span data-ttu-id="00708-123">Настройка переключателя трассировки выполняется для ее включения и отключения или для задания ее уровня, определяющего количество и тип сообщений, передаваемых в прослушиватели.</span><span class="sxs-lookup"><span data-stu-id="00708-123">You configure a trace switch to turn it on and off, or to set its level, determining the amount and type of messages it passes along to listeners.</span></span>  
  
 <span data-ttu-id="00708-124">Настройка переключателей выполняется с помощью файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="00708-124">Your switches are configured using the .config file.</span></span> <span data-ttu-id="00708-125">Для веб-приложения это файл Web.config, связанный с проектом.</span><span class="sxs-lookup"><span data-stu-id="00708-125">For a Web application, this is the Web.config file associated with the project.</span></span> <span data-ttu-id="00708-126">В приложении Windows этот файл называется (имя приложения). В развернутом приложении этот файл должен находиться в той же папке, что и исполняемая.</span><span class="sxs-lookup"><span data-stu-id="00708-126">In a Windows application, this file is named (application name).exe.config. In a deployed application, this file must reside in the same folder as the executable.</span></span>  
  
 <span data-ttu-id="00708-127">Когда приложение выполняет код, который создает экземпляр переключателя в первый раз, оно проверяет в файле конфигурации сведения уровня трассировки для именованного переключателя.</span><span class="sxs-lookup"><span data-stu-id="00708-127">When your application executes the code that creates an instance of a switch for the first time, it checks the configuration file for trace-level information about the named switch.</span></span> <span data-ttu-id="00708-128">Система трассировки проверяет файл конфигурации для каждого конкретного переключателя только один раз — при первом создании переключателя приложением.</span><span class="sxs-lookup"><span data-stu-id="00708-128">The tracing system examines the configuration file only once for any particular switch — the first time your application creates the switch.</span></span>  
  
 <span data-ttu-id="00708-129">В развернутом приложении вы включаете код трассировки путем повторной настройки объектов переключателей, когда приложение не запущено.</span><span class="sxs-lookup"><span data-stu-id="00708-129">In a deployed application, you enable trace code by reconfiguring switch objects when your application is not running.</span></span> <span data-ttu-id="00708-130">Обычно это подразумевает включение и отключение объектов переключателей или изменение уровней трассировки, а затем перезапуск приложения.</span><span class="sxs-lookup"><span data-stu-id="00708-130">Typically this involves turning the switch objects on and off or by changing the tracing levels, and then restarting your application.</span></span>  
  
 <span data-ttu-id="00708-131">При создании экземпляра переключателя вы также инициализируете его, указывая два аргумента: *displayName* и *description*.</span><span class="sxs-lookup"><span data-stu-id="00708-131">When you create an instance of a switch, you also initialize it by specifying two arguments: a *displayName* argument and a *description* argument.</span></span> <span data-ttu-id="00708-132">Аргумент *displayName* конструктора устанавливает свойство <xref:System.Diagnostics.Switch.DisplayName%2A?displayProperty=nameWithType> экземпляра класса <xref:System.Diagnostics.Switch>.</span><span class="sxs-lookup"><span data-stu-id="00708-132">The *displayName* argument of the constructor sets the <xref:System.Diagnostics.Switch.DisplayName%2A?displayProperty=nameWithType> property of the <xref:System.Diagnostics.Switch> class instance.</span></span> <span data-ttu-id="00708-133">Аргумент *displayName* — это имя, которое используется для настройки переключателя в файле .config, а аргумент *description* должен возвращать краткое описание переключателя и тип сообщений, которыми он управляет.</span><span class="sxs-lookup"><span data-stu-id="00708-133">The *displayName* is the name that is used to configure the switch in the .config file, and the *description* argument should return a brief description of the switch and what messages it controls.</span></span>  
  
 <span data-ttu-id="00708-134">Помимо указания имени переключателя для настройки вы также должны указать значение для этого переключателя.</span><span class="sxs-lookup"><span data-stu-id="00708-134">In addition to specifying the name of a switch to configure, you must also specify a value for the switch.</span></span> <span data-ttu-id="00708-135">Это значение представляет собой целое число.</span><span class="sxs-lookup"><span data-stu-id="00708-135">This value is an Integer.</span></span> <span data-ttu-id="00708-136">Для <xref:System.Diagnostics.BooleanSwitch> значение 0 соответствует значению **Off** (отключено), а любое ненулевое значение соответствует значению **On** (включено).</span><span class="sxs-lookup"><span data-stu-id="00708-136">For <xref:System.Diagnostics.BooleanSwitch>, a value of 0 corresponds to **Off**, and any nonzero value corresponds to **On**.</span></span> <span data-ttu-id="00708-137">Для <xref:System.Diagnostics.TraceSwitch> числа 0, 1, 2, 3 и 4 означают **Off** (отключено), **Error** (ошибка), **Warning** (предупреждение), **Info** (сведения) и **Verbose** (подробные сведения), соответственно.</span><span class="sxs-lookup"><span data-stu-id="00708-137">For <xref:System.Diagnostics.TraceSwitch>, 0,1,2,3, and 4 correspond **Off**, **Error**, **Warning**, **Info**, and **Verbose**, respectively.</span></span> <span data-ttu-id="00708-138">Любое число больше 4 интерпретируется как значение **Verbose** (подробно), а любое число меньше нуля — как значение **Off** (отключено).</span><span class="sxs-lookup"><span data-stu-id="00708-138">Any number greater than 4 is treated as **Verbose**, and any number less than zero is treated as **Off**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="00708-139">В .NET Framework версии 2.0 для указания значения переключателя можно использовать текст.</span><span class="sxs-lookup"><span data-stu-id="00708-139">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="00708-140">Например, значение `true` для <xref:System.Diagnostics.BooleanSwitch> или текст, представляющий значение перечисления, такой как `Error`, для <xref:System.Diagnostics.TraceSwitch>.</span><span class="sxs-lookup"><span data-stu-id="00708-140">For example, `true` for a <xref:System.Diagnostics.BooleanSwitch> or the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="00708-141">Строка `<add name="myTraceSwitch" value="Error" />` эквивалентна `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="00708-141">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
 <span data-ttu-id="00708-142">Чтобы конечные пользователи могли настраивать переключатели трассировки приложения, вы должны предоставить подробную документацию по переключателям в своем приложении.</span><span class="sxs-lookup"><span data-stu-id="00708-142">In order for end users to be able to configure an application's trace switches, you must provide detailed documentation on the switches in your application.</span></span> <span data-ttu-id="00708-143">Необходимо подробно описать, какие переключатели чем управляют и как их включать и отключать.</span><span class="sxs-lookup"><span data-stu-id="00708-143">You should detail which switches control what and how to turn them on and off.</span></span> <span data-ttu-id="00708-144">Вы также должны предоставить конечному пользователю файл конфигурации с соответствующей справкой в комментариях.</span><span class="sxs-lookup"><span data-stu-id="00708-144">You should also provide your end user with a .config file that has appropriate Help in the comments.</span></span>  
  
#### <a name="to-configure-trace-switches"></a><span data-ttu-id="00708-145">Конфигурация коммутаторов трассировки</span><span class="sxs-lookup"><span data-stu-id="00708-145">To configure trace switches</span></span>  
  
1. <span data-ttu-id="00708-146">Чтобы использовать переключатели трассировки, необходимо сначала создать их в коде, как описано в разделе [Создание и инициализация переключателя трассировки](#create).</span><span class="sxs-lookup"><span data-stu-id="00708-146">In order to use trace switches, you must first create them and place them in your code as described in the section [Creating and initializing a trace switch](#create).</span></span>  
  
2. <span data-ttu-id="00708-147">Если в проекте отсутствует файл конфигурации (app.config или Web.config), выберите **Добавить новый элемент** в меню **Проект**.</span><span class="sxs-lookup"><span data-stu-id="00708-147">If your project does not contain a configuration file (app.config or Web.config), then from the **Project** menu, select **Add New Item**.</span></span>  
  
    - <span data-ttu-id="00708-148">**Visual Basic:** в диалоговом окне **Добавление нового элемента** выберите элемент **Файл конфигурации приложения**.</span><span class="sxs-lookup"><span data-stu-id="00708-148">**Visual Basic:** In the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
         <span data-ttu-id="00708-149">Файл конфигурации приложения создается и открывается.</span><span class="sxs-lookup"><span data-stu-id="00708-149">The application configuration file is created and opened.</span></span> <span data-ttu-id="00708-150">Это документ XML с корневым элементом `<configuration>.`</span><span class="sxs-lookup"><span data-stu-id="00708-150">This is an XML document whose root element is `<configuration>.`</span></span>  
  
    - <span data-ttu-id="00708-151">**Visual C#:** в диалоговом окне **Добавление нового элемента** выберите элемент **XML-файл**.</span><span class="sxs-lookup"><span data-stu-id="00708-151">**Visual C#:** In the **Add New Item** dialog box, choose **XML File**.</span></span> <span data-ttu-id="00708-152">Назовите этот файл **app.config**. В редакторxML после декларации XML добавьте следующее XML:</span><span class="sxs-lookup"><span data-stu-id="00708-152">Name this file **app.config**. In the XML editor, after the XML declaration, add the following XML:</span></span>  
  
        ```xml  
        <configuration>  
        </configuration>  
        ```  
  
         <span data-ttu-id="00708-153">При компиляции проекта файл app.config копируется в выходную папку проекта и получает новое имя: *имя_приложения*.exe.config.</span><span class="sxs-lookup"><span data-stu-id="00708-153">When your project is compiled, the app.config file is copied to the project output folder and is renamed *applicationname*.exe.config.</span></span>  
  
3. <span data-ttu-id="00708-154">Добавьте соответствующий код XML для настройки переключателей между тегами `<configuration>` и `</configuration>`.</span><span class="sxs-lookup"><span data-stu-id="00708-154">After the `<configuration>` tag but before the `</configuration>` tag, add the appropriate XML to configure your switches.</span></span> <span data-ttu-id="00708-155">В следующих примерах приведены переключатели **BooleanSwitch** (со свойством **DisplayName**, равным `DataMessageSwitch`) и **TraceSwitch** (со свойством **DisplayName**, равным `TraceLevelSwitch`).</span><span class="sxs-lookup"><span data-stu-id="00708-155">The following examples demonstrate a **BooleanSwitch** with a **DisplayName** property of `DataMessageSwitch` and a **TraceSwitch** with a **DisplayName** property of `TraceLevelSwitch`.</span></span>  
  
    ```xml  
    <system.diagnostics>  
       <switches>  
          <add name="DataMessagesSwitch" value="0" />  
          <add name="TraceLevelSwitch" value="0" />  
       </switches>  
    </system.diagnostics>  
    ```  
  
     <span data-ttu-id="00708-156">В данной конфигурации оба переключателя отключены.</span><span class="sxs-lookup"><span data-stu-id="00708-156">In this configuration, both switches are off.</span></span>  
  
4. <span data-ttu-id="00708-157">Если необходимо включить переключатель **BooleanSwitch**, например `DataMessagesSwitch` в предыдущем примере, измените свойство **Value** на любое целое число, отличное от 0.</span><span class="sxs-lookup"><span data-stu-id="00708-157">If you need to turn on a **BooleanSwitch**, such as `DataMessagesSwitch` shown in the previous example, change the **Value** to any integer other than 0.</span></span>  
  
5. <span data-ttu-id="00708-158">Если необходимо включить переключатель **TraceSwitch**, например `TraceLevelSwitch` в предыдущем примере, измените свойство **Value** на подходящее значение уровня (от 1 до 4).</span><span class="sxs-lookup"><span data-stu-id="00708-158">If you need to turn on a **TraceSwitch**, such as `TraceLevelSwitch` shown in the previous example, change the **Value** to the appropriate level setting (1 to 4).</span></span>  
  
6. <span data-ttu-id="00708-159">Добавьте комментарии в файл конфигурации, чтобы конечный пользователь имел четкое представление, какие значения следует изменять для соответствующей настройки переключателей.</span><span class="sxs-lookup"><span data-stu-id="00708-159">Add comments to the .config file so the end user has a clear understanding of what values to change to configure the switches appropriately.</span></span>  
  
     <span data-ttu-id="00708-160">В следующем примере показано, как может выглядеть окончательный код, включая комментарии:</span><span class="sxs-lookup"><span data-stu-id="00708-160">The following example shows how the final code, including comments, might look:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="00708-161">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="00708-161">See also</span></span>

- [<span data-ttu-id="00708-162">Трассировка и оборудование приложений</span><span class="sxs-lookup"><span data-stu-id="00708-162">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
- [<span data-ttu-id="00708-163">Практическое руководство. Добавление операторов трассировки в код приложения</span><span class="sxs-lookup"><span data-stu-id="00708-163">How to: Add Trace Statements to Application Code</span></span>](how-to-add-trace-statements-to-application-code.md)
- [<span data-ttu-id="00708-164">Переключатели трассировки</span><span class="sxs-lookup"><span data-stu-id="00708-164">Trace Switches</span></span>](trace-switches.md)
- [<span data-ttu-id="00708-165">Схема настроек трассировки и отпараги</span><span class="sxs-lookup"><span data-stu-id="00708-165">Trace and Debug Settings Schema</span></span>](../configure-apps/file-schema/trace-debug/index.md)
