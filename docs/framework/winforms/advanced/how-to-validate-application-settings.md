---
title: Как выполнить Проверка параметров приложения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating application settings
- application settings [Windows Forms], Windows Forms
- application settings [Windows Forms], validating
ms.assetid: 9f145ada-4267-436a-aa4c-c4dcffd0afb7
ms.openlocfilehash: 6ebdf1ee74e3ed41b02fdeb545ffc57aaa2d6d7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496290"
---
# <a name="how-to-validate-application-settings"></a><span data-ttu-id="efb34-102">Как выполнить Проверка параметров приложения</span><span class="sxs-lookup"><span data-stu-id="efb34-102">How to: Validate Application Settings</span></span>
<span data-ttu-id="efb34-103">В этом разделе показано, как проверить параметры приложения перед их сохранением.</span><span class="sxs-lookup"><span data-stu-id="efb34-103">This topic demonstrates how to validate application settings before they are persisted.</span></span>  
  
 <span data-ttu-id="efb34-104">Поскольку параметры приложений являются строго типизированными, это дает некоторую уверенность в том, что пользователи не могут назначить тому или иному параметру данные неверного типа.</span><span class="sxs-lookup"><span data-stu-id="efb34-104">Because application settings are strongly typed, you have some confidence that users cannot assign data of an incorrect type to a given setting.</span></span> <span data-ttu-id="efb34-105">Тем не менее, пользователь по-прежнему может попытаться присвоить значение вне допустимого диапазона, наприме указать дату рождения в будущем.</span><span class="sxs-lookup"><span data-stu-id="efb34-105">However, a user still may attempt to assign a value to a setting that falls outside of acceptable bounds—for example, supplying a birth date that occurs in the future.</span></span> <span data-ttu-id="efb34-106"><xref:System.Configuration.ApplicationSettingsBase>, родительским классом для всех классов параметров приложения, предоставляет четыре события для проверки границ.</span><span class="sxs-lookup"><span data-stu-id="efb34-106"><xref:System.Configuration.ApplicationSettingsBase>, the parent class of all application settings classes, exposes four events to enable such bounds checking.</span></span> <span data-ttu-id="efb34-107">Благодаря обработке этих событий весь код проверки размещается в одном месте, а не в разных частях проекта.</span><span class="sxs-lookup"><span data-stu-id="efb34-107">Handling these events puts all of your validation code in a single location, rather than scattering it throughout your project.</span></span>  
  
 <span data-ttu-id="efb34-108">Используемое событие зависит от времени, когда необходимо проверить параметры, как описано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="efb34-108">The event you use depends upon when you need to validate your settings, as described in the following table.</span></span>  
  
|<span data-ttu-id="efb34-109">событие</span><span class="sxs-lookup"><span data-stu-id="efb34-109">Event</span></span>|<span data-ttu-id="efb34-110">Вхождение и использование</span><span class="sxs-lookup"><span data-stu-id="efb34-110">Occurrence and use</span></span>|  
|-----------|------------------------|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsLoaded>|<span data-ttu-id="efb34-111">Возникает после начальной загрузки группы свойств параметров.</span><span class="sxs-lookup"><span data-stu-id="efb34-111">Occurs after the initial loading of a settings property group.</span></span><br /><br /> <span data-ttu-id="efb34-112">Используйте это событие для проверки начальных значений для всей группы свойств перед их применением в приложении.</span><span class="sxs-lookup"><span data-stu-id="efb34-112">Use this event to validate initial values for the entire property group before they are used within the application.</span></span>|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingChanging>|<span data-ttu-id="efb34-113">Происходит перед изменением значения одного свойства параметров.</span><span class="sxs-lookup"><span data-stu-id="efb34-113">Occurs before the value of a single settings property is changed.</span></span><br /><br /> <span data-ttu-id="efb34-114">Используйте это событие для проверки одного свойства до его изменения.</span><span class="sxs-lookup"><span data-stu-id="efb34-114">Use this event to validate a single property before it is changed.</span></span> <span data-ttu-id="efb34-115">Оно позволяет пользователям немедленно получить сведения о своих действиях и решениях.</span><span class="sxs-lookup"><span data-stu-id="efb34-115">It can provide immediate feedback to users regarding their actions and choices.</span></span>|  
|<xref:System.Configuration.ApplicationSettingsBase.PropertyChanged>|<span data-ttu-id="efb34-116">Происходит после изменения значения одного свойства параметра.</span><span class="sxs-lookup"><span data-stu-id="efb34-116">Occurs after the value of a single settings property is changed.</span></span><br /><br /> <span data-ttu-id="efb34-117">Используйте это событие для проверки одного свойства после его изменения.</span><span class="sxs-lookup"><span data-stu-id="efb34-117">Use this event to validate a single property after it is changed.</span></span> <span data-ttu-id="efb34-118">Это событие редко используется для проверки, если не требуется длительный процесс асинхронной проверки.</span><span class="sxs-lookup"><span data-stu-id="efb34-118">This event is rarely used for validation unless a lengthy, asynchronous validation process is required.</span></span>|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>|<span data-ttu-id="efb34-119">Возникает перед сохранением группы свойств параметров.</span><span class="sxs-lookup"><span data-stu-id="efb34-119">Occurs before the settings property group is stored.</span></span><br /><br /> <span data-ttu-id="efb34-120">Используйте это событие для проверки значений для всей группы свойств перед их сохранением на диске.</span><span class="sxs-lookup"><span data-stu-id="efb34-120">Use this event to validate values for the entire property group before they are persisted to disk.</span></span>|  
  
 <span data-ttu-id="efb34-121">Как правило, в целях проверки все эти события внутри одного приложения не используются.</span><span class="sxs-lookup"><span data-stu-id="efb34-121">Typically, you will not use all of these events within the same application for validation purposes.</span></span> <span data-ttu-id="efb34-122">Например, часто бывает можно выполнить все требования по проверке путем обработки только <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> событий.</span><span class="sxs-lookup"><span data-stu-id="efb34-122">For example, it is often possible to fulfill all validation requirements by handling only the <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> event.</span></span>  
  
 <span data-ttu-id="efb34-123">Обычно при обнаружении недопустимого значения обработчик событий выполняет одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="efb34-123">An event handler generally performs one of the following actions when it detects an invalid value:</span></span>  
  
-   <span data-ttu-id="efb34-124">Автоматически предоставляет заведомо правильное значение, например значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="efb34-124">Automatically supplies a value known to be correct, such as the default value.</span></span>  
  
-   <span data-ttu-id="efb34-125">Повторно запрашивает сведения у пользователя серверного кода.</span><span class="sxs-lookup"><span data-stu-id="efb34-125">Re-queries the user of server code for information.</span></span>  
  
-   <span data-ttu-id="efb34-126">Для событий, возникающих до связанных с ними действий, таких как <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> и <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>, использует <xref:System.ComponentModel.CancelEventArgs> аргумент для отмены операции.</span><span class="sxs-lookup"><span data-stu-id="efb34-126">For events raised before their associated actions, such as <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> and <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>, uses the <xref:System.ComponentModel.CancelEventArgs> argument to cancel the operation.</span></span>  
  
 <span data-ttu-id="efb34-127">Дополнительные сведения об обработке событий см. в разделе [Общие сведения об обработчиках событий](../../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="efb34-127">For more information about event handling, see [Event Handlers Overview](../../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).</span></span>  
  
 <span data-ttu-id="efb34-128">Следующие процедуры показывают, как для проверки корректности даты рождения с помощью <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> или <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> событий.</span><span class="sxs-lookup"><span data-stu-id="efb34-128">The following procedures show how to test for a valid birth date using either the <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> or the <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> event.</span></span> <span data-ttu-id="efb34-129">В этих процедурах предполагается, что вы уже создали параметры приложения. В этом примере будет выполнена проверка границ для параметра с именем `DateOfBirth`.</span><span class="sxs-lookup"><span data-stu-id="efb34-129">The procedures were written under the assumption that you have already created your application settings; in this example, we will perform bounds checking on a setting named `DateOfBirth`.</span></span> <span data-ttu-id="efb34-130">Дополнительные сведения о создании параметров см. в разделе [как: Создание параметров приложения](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).</span><span class="sxs-lookup"><span data-stu-id="efb34-130">For more information about creating settings, see [How to: Create Application Settings](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).</span></span>  
  
### <a name="to-obtain-the-application-settings-object"></a><span data-ttu-id="efb34-131">Получение объекта параметров приложения</span><span class="sxs-lookup"><span data-stu-id="efb34-131">To obtain the application settings object</span></span>  
  
-   <span data-ttu-id="efb34-132">Для получения ссылки на объект параметров приложения (экземпляр программы-оболочки) выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="efb34-132">Obtain a reference to the application settings object (the wrapper instance) by completing one of the following bulleted items:</span></span>  
  
    -   <span data-ttu-id="efb34-133">Если вы создали параметры в диалоговом окне «Параметры приложения Visual Studio» в **редакторе свойств**, объект параметров по умолчанию, созданный для вашего языка, можно получить с помощью следующего выражения.</span><span class="sxs-lookup"><span data-stu-id="efb34-133">If you created your settings using the Visual Studio Application Settings dialog box in the **Property Editor**, you can retrieve the default settings object generated for your language through the following expression.</span></span>  
  
        ```csharp  
        Configuration.Settings.Default   
        ```  
  
        ```vb  
        MySettings.Default   
        ```  
  
         <span data-ttu-id="efb34-134">- или -</span><span class="sxs-lookup"><span data-stu-id="efb34-134">-or-</span></span>  
  
    -   <span data-ttu-id="efb34-135">Если вы являетесь разработчиком на Visual Basic и создали параметры приложения с помощью конструктора проектов, для извлечения параметров можно использовать [объект My.Settings](~/docs/visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="efb34-135">If you are a Visual Basic developer and you created your application settings using the Project Designer, you can retrieve your settings by using the [My.Settings Object](~/docs/visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
         <span data-ttu-id="efb34-136">- или -</span><span class="sxs-lookup"><span data-stu-id="efb34-136">-or-</span></span>  
  
    -   <span data-ttu-id="efb34-137">Если параметры были созданы путем наследования от <xref:System.Configuration.ApplicationSettingsBase> напрямую, необходимо создать экземпляр класса вручную.</span><span class="sxs-lookup"><span data-stu-id="efb34-137">If you created your settings by deriving from <xref:System.Configuration.ApplicationSettingsBase> directly, you need to instantiate your class manually.</span></span>  
  
        ```csharp  
        MyCustomSettings settings = new MyCustomSettings();  
        ```  
  
        ```vb  
        Dim Settings as New MyCustomSettings()  
        ```  
  
 <span data-ttu-id="efb34-138">В следующих процедурах предполагается, что объект параметров приложения получен путем выполнения последнего действия в этой процедуре.</span><span class="sxs-lookup"><span data-stu-id="efb34-138">The following procedures were written under the assumption that the application settings object was obtained by completing the last bulleted item in this procedure.</span></span>  
  
### <a name="to-validate-application-settings-when-a-setting-is-changing"></a><span data-ttu-id="efb34-139">Проверка параметров приложения при изменении параметра</span><span class="sxs-lookup"><span data-stu-id="efb34-139">To validate Application Settings when a setting is changing</span></span>  
  
1.  <span data-ttu-id="efb34-140">Если вы являетесь C# developer, в формы или элемента управления `Load` событий, добавьте обработчик событий для <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> событий.</span><span class="sxs-lookup"><span data-stu-id="efb34-140">If you are a C# developer, in your form or control's `Load` event, add an event handler for the <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> event.</span></span>  
  
     <span data-ttu-id="efb34-141">- или -</span><span class="sxs-lookup"><span data-stu-id="efb34-141">-or-</span></span>  
  
     <span data-ttu-id="efb34-142">Если вы являетесь разработчиком на Visual Basic, объявите переменную `Settings` с помощью ключевого слова `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="efb34-142">If you are a Visual Basic developer, you should declare the `Settings` variable using the `WithEvents` keyword.</span></span>  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        settings.SettingChanging += new SettingChangingEventHandler(MyCustomSettings_SettingChanging);  
    }  
    ```  
  
    ```vb  
    Public Sub Form1_Load(sender as Object, e as EventArgs)  
        AddHandler settings.SettingChanging, AddressOf MyCustomSettings_SettingChanging  
    End Sub   
    ```  
  
2.  <span data-ttu-id="efb34-143">Определите обработчик событий и напишите внутри него код для выполнения проверки границ для даты рождения.</span><span class="sxs-lookup"><span data-stu-id="efb34-143">Define the event handler, and write the code inside of it to perform bounds checking on the birth date.</span></span>  
  
    ```csharp  
    private void MyCustomSettings_SettingChanging(Object sender, SettingChangingEventArgs e)  
    {  
        if (e.SettingName.Equals("DateOfBirth")) {  
            Date newDate = (Date)e.NewValue;  
            If (newDate > Date.Now) {  
                e.Cancel = true;  
                // Inform the user.  
            }  
        }  
    }  
    ```  
  
    ```vb  
    Private Sub MyCustomSettings_SettingChanging(sender as Object, e as SettingChangingEventArgs) Handles Settings.SettingChanging  
        If (e.SettingName.Equals("DateOfBirth")) Then  
            Dim NewDate as Date = CType(e.NewValue, Date)  
            If (NewDate > Date.Now) Then  
                e.Cancel = True  
                ' Inform the user.  
            End If  
        End If  
    End Sub  
    ```  
  
### <a name="to-validate-application-settings-when-a-save-occurs"></a><span data-ttu-id="efb34-144">Проверка параметров приложения в ходе сохранения</span><span class="sxs-lookup"><span data-stu-id="efb34-144">To validate Application Settings when a Save occurs</span></span>  
  
1.  <span data-ttu-id="efb34-145">В своей форме или элемента управления `Load` событий, добавьте обработчик событий для <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> событий.</span><span class="sxs-lookup"><span data-stu-id="efb34-145">In your form or control's `Load` event, add an event handler for the <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> event.</span></span>  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        settings.SettingsSaving += new SettingsSavingEventHandler(MyCustomSettings_SettingsSaving);  
    }  
    ```  
  
    ```vb  
    Public Sub Form1_Load(Sender as Object, e as EventArgs)  
        AddHandler settings.SettingsSaving, AddressOf MyCustomSettings_SettingsSaving  
    End Sub  
    ```  
  
2.  <span data-ttu-id="efb34-146">Определите обработчик событий и напишите внутри него код для выполнения проверки границ для даты рождения.</span><span class="sxs-lookup"><span data-stu-id="efb34-146">Define the event handler, and write the code inside of it to perform bounds checking on the birth date.</span></span>  
  
    ```csharp  
    private void MyCustomSettings_SettingsSaving(Object sender, SettingsSavingEventArgs e)  
    {  
        if (this["DateOfBirth"] > Date.Now) {  
            e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Private Sub MyCustomSettings_SettingsSaving(Sender as Object, e as SettingsSavingEventArgs)  
        If (Me["DateOfBirth"] > Date.Now) Then  
            e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="efb34-147">См. также</span><span class="sxs-lookup"><span data-stu-id="efb34-147">See also</span></span>
- [<span data-ttu-id="efb34-148">Создание обработчиков событий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="efb34-148">Creating Event Handlers in Windows Forms</span></span>](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="efb34-149">Практическое руководство. Создание параметров приложения</span><span class="sxs-lookup"><span data-stu-id="efb34-149">How to: Create Application Settings</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)
