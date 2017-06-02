---
title: "Additional Security Considerations in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Windows API, secure calls"
  - "Windows Forms, secure calls to Windows API"
  - "Windows API, calling"
  - "APIs, calling"
  - "security [Windows Forms]"
  - "Windows API, Windows Forms security settings"
  - "API calls, Windows Forms security settings"
  - "security [Windows Forms], calling APIs"
  - "Clipboard, securing access"
ms.assetid: 15abda8b-0527-47c7-aedb-77ab595f2bf1
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Additional Security Considerations in Windows Forms
Параметры безопасности [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] могут привести к тому, что приложение будет работать по\-разному в среде с частичным доверием и на локальном компьютере.  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] ограничивает доступ к таким важным локальным ресурсам, как файловая система, сеть, неуправляемые интерфейсы API и пр.  Параметры безопасности влияют на возможность вызова интерфейса Microsoft Win32 API или других интерфейсов API, которые нельзя проверить с помощью системы безопасности.  Безопасность также влияет на другие аспекты приложения, включая доступ к файлам и данным, а также печать.  Дополнительные сведения о доступе к файлам и данным в среде с частичным доверием см. в разделе [More Secure File and Data Access in Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md).  Дополнительные сведения о печати в среде с частичным доверием см. в разделе [More Secure Printing in Windows Forms](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md).  
  
 В следующих разделах обсуждаются способы работы с буфером обмена, выполнения действий с окнами и вызова интерфейса Win32 API из приложений, работающих в среде с частичным доверием.  
  
## Доступ к буферу обмена  
 Класс <xref:System.Security.Permissions.UIPermission> управляет доступом к в буферу обмена, а связанное значение перечисления <xref:System.Security.Permissions.UIPermissionClipboard> указывает уровень доступа.  В следующей таблице представлены возможные уровни разрешений.  
  
|Значение UIPermissionClipboard|Описание|  
|------------------------------------|--------------|  
|<xref:System.Security.Permissions.UIPermissionClipboard>|Буфер обмена можно использовать без ограничений.|  
|<xref:System.Security.Permissions.UIPermissionClipboard>|Буфер обмена можно использовать с некоторыми ограничениями.  Помещение данных в буфер обмена \(команды копирования и вырезания\) не ограничивается.  Встроенные элементы управления, которые допускают использование команды вставки, например текстовые поля, могут допускать вставку данных из буфера обмена, однако пользовательские элементы управления не могут программно считывать данные из буфера обмена.|  
|<xref:System.Security.Permissions.UIPermissionClipboard>|Использовать буфер обмена запрещено.|  
  
 По умолчанию зона локальной интрасети получает уровень доступа <xref:System.Security.Permissions.UIPermissionClipboard>, а зона Интернета — уровень доступа <xref:System.Security.Permissions.UIPermissionClipboard>.  Это означает, что приложение может копировать данные в буфер обмена, но не может программно вставлять или считывать данные из буфера обмена.  Такие ограничения не позволяют частично доверенным приложениям считывать содержимое буфера обмена, скопированное туда другими приложениями.  Если приложению требуется полный доступ к буферу обмена, но соответствующее разрешение отсутствует, необходимо повысить уровень разрешений для приложения.  Дополнительные сведения о повышении уровня разрешений см. в разделе [Общее администрирование политики безопасности](http://msdn.microsoft.com/ru-ru/5121fe35-f0e3-402c-94ab-4f35b0a87b4b).  
  
## Операции с окнами  
 Класс <xref:System.Security.Permissions.UIPermission> также управляет разрешениями на выполнение действий с окнами и другими действиями, связанными с интерфейсом пользователя; уровень доступа указывается значением перечисления <xref:System.Security.Permissions.UIPermissionWindow>.  В следующей таблице представлены возможные уровни разрешений.  
  
 По умолчанию зона локальной интрасети получает уровень доступа <xref:System.Security.Permissions.UIPermissionWindow>, а зона Интернета — уровень доступа <xref:System.Security.Permissions.UIPermissionWindow>.  Таким образом, в зоне Интернета приложение может выполнять большинство операций с окнами и элементами пользовательского интерфейса, однако внешний вид окон будет изменен.  Измененное окно отображает при первом запуске всплывающее уведомление, содержит измененный текст в строке заголовка и требует наличия кнопки закрытия в строке заголовка.  Всплывающее уведомление и строка заголовка показывают, что приложение запущено в режиме частичного доверия.  
  
|Значение UIPermissionWindow|Описание|  
|---------------------------------|--------------|  
|<xref:System.Security.Permissions.UIPermissionWindow>|Пользователи могут использовать все окна и все события пользовательского ввода без ограничений.|  
|<xref:System.Security.Permissions.UIPermissionWindow>|Пользователи могут использовать только безопасные окна верхнего уровня и безопасные подокна для рисования; события пользовательского ввода для пользовательского интерфейса можно использовать только в этих окнах верхнего уровня и подокнах.  Такие безопасные окна ясно обозначены и имеют ограничения на минимальный и максимальный размер.  Эти ограничения предотвращают потенциально опасные атаки подмены, такие как имитация экрана входа в систему или рабочего стола системы, и не позволяют получать программный доступ к родительским окнам, интерфейсам API, связанным с фокусом, и использовать элемент управления <xref:System.Windows.Forms.ToolTip>,|  
|<xref:System.Security.Permissions.UIPermissionWindow>|Пользователи могут использовать только безопасные подокна для рисования и только события пользовательского ввода для пользовательского интерфейса в этих подокнах.  Элемент управления, отображаемый в браузере, — пример такого безопасного подокна.|  
|<xref:System.Security.Permissions.UIPermissionWindow>|Пользователи не могут использовать окна или события пользовательского интерфейса.  Использовать пользовательский интерфейс запрещено.|  
  
 Каждый уровень разрешений, определенный перечислением <xref:System.Security.Permissions.UIPermissionWindow>, позволяет выполнять меньшее количество действий, чем предыдущий уровень.  В следующей таблице указаны действия, которые ограничены значениями <xref:System.Security.Permissions.UIPermissionWindow> и <xref:System.Security.Permissions.UIPermissionWindow>.  Точные разрешения, требуемые для каждого члена, приведены в разделах, относящихся к этому члену в документации по библиотеке классов .NET Framework.  
  
 Разрешение <xref:System.Security.Permissions.UIPermissionWindow> ограничивает действия, приведенные в следующей таблице.  
  
|Компонент|Действия, на которые наложено ограничение|  
|---------------|-----------------------------------------------|  
|<xref:System.Windows.Forms.Application>|-   Задание свойства <xref:System.Windows.Forms.Application.SafeTopLevelCaptionFormat%2A>.|  
|<xref:System.Windows.Forms.Control>|-   Чтение свойства <xref:System.Windows.Forms.Control.Parent%2A>.<br />-   Задание свойства `Region`.<br />-   Вызов методов <xref:System.Windows.Forms.Control.FindForm%2A>, <xref:System.Windows.Forms.Control.Focus%2A>, <xref:System.Windows.Forms.Control.FromChildHandle%2A> и <xref:System.Windows.Forms.Control.FromHandle%2A>, <xref:System.Windows.Forms.Control.PreProcessMessage%2A>, <xref:System.Windows.Forms.Control.ReflectMessage%2A> или <xref:System.Windows.Forms.Control.SetTopLevel%2A>.<br />-   Вызов метода <xref:System.Windows.Forms.Control.GetChildAtPoint%2A>, если возвращенный элемент управления не является дочерним по отношению к вызывающему элементу управления.<br />-   Изменение фокуса элемента управления в контейнерном элементе управления.|  
|<xref:System.Windows.Forms.Cursor>|-   Задание свойства <xref:System.Windows.Forms.Cursor.Clip%2A>.<br />-   Вызов метода <xref:System.Windows.Forms.Control.Hide%2A>.|  
|<xref:System.Windows.Forms.DataGrid>|-   Вызов метода <xref:System.Windows.Forms.ContainerControl.ProcessTabKey%2A>.|  
|<xref:System.Windows.Forms.Form>|-   Чтение свойства <xref:System.Windows.Forms.Form.ActiveForm%2A> или <xref:System.Windows.Forms.Form.MdiParent%2A>.<br />-   Задание свойства <xref:System.Windows.Forms.Form.ControlBox%2A>, <xref:System.Windows.Forms.Form.ShowInTaskbar%2A> или<xref:System.Windows.Forms.Form.TopMost%2A>.<br />-   Задание значения свойства <xref:System.Windows.Forms.Form.Opacity%2A> ниже 50 %.<br />-   Задание для свойства <xref:System.Windows.Forms.Form.WindowState%2A> значения <xref:System.Windows.Forms.FormWindowState> программными средствами.<br />-   Вызов метода <xref:System.Windows.Forms.Form.Activate%2A>.<br />-   Использование значений перечисления <xref:System.Windows.Forms.FormBorderStyle>, <xref:System.Windows.Forms.FormBorderStyle> и <xref:System.Windows.Forms.FormBorderStyle> <xref:System.Windows.Forms.FormBorderStyle>.|  
|<xref:System.Windows.Forms.NotifyIcon>|-   Использование компонента <xref:System.Windows.Forms.NotifyIcon> полностью запрещено.|  
  
 Значение <xref:System.Security.Permissions.UIPermissionWindow> ограничивает действия, приведенные в следующей таблице, в дополнение к ограничениям, наложенным значением <xref:System.Security.Permissions.UIPermissionWindow>.  
  
|Компонент|Действия, на которые наложено ограничение|  
|---------------|-----------------------------------------------|  
|<xref:System.Windows.Forms.CommonDialog>|-   Отображение диалогового окна, производного от класса <xref:System.Windows.Forms.CommonDialog>.|  
|<xref:System.Windows.Forms.Control>|-   Вызов метода <xref:System.Windows.Forms.Control.CreateGraphics%2A>.<br />-   Задание свойства <xref:System.Windows.Forms.Control.Cursor%2A>.|  
|<xref:System.Windows.Forms.Control.Cursor%2A>|-   Задание свойства <xref:System.Windows.Forms.Cursor.Current%2A>.|  
|<xref:System.Windows.Forms.MessageBox>|-   Вызов метода <xref:System.Windows.Forms.Form.Show%2A>.|  
  
### Размещение элементов управления сторонних производителей  
 Другой тип управления окном может использоваться, если в форме размещены элементы управления сторонних производителей.  Элементом управления стороннего производителя называется любой пользовательский элемент управления <xref:System.Windows.Forms.UserControl>, который разрабатывался и компилировался не самостоятельно.  Хотя сценарием размещения сложно воспользоваться, существует теоретическая возможность расширения независимым элементом управления своей области отрисовки на всю область формы.  Этот элемент управления может имитировать критическое диалоговое окно, а затем запросить сведения, такие как имя пользователя\/пароль или номера банковских счетов от пользователей.  
  
 Чтобы ограничить эту потенциальную угрозу, используйте сторонние элементы управления только от доверенных поставщиков.  Если используется элемент управления стороннего производителя, загруженный из непроверенного источника, рекомендуется просмотреть исходный код на предмет потенциальных угроз.  После проверки того, что источник не является вредоносным, следует скомпилировать сборку вручную, чтобы убедиться, что источник соответствует сборке.  
  
## Вызовы интерфейса Win32 API  
 Если при разработке приложения требуется вызвать функцию из интерфейса Win32 API, происходит доступ к неуправляемому коду.  В этом случае действия программы по отношению к окнам или операционной системе при работе с вызовами Win32 API или с его значениями определить невозможно.  Класс <xref:System.Security.Permissions.SecurityPermission> и значение <xref:System.Security.Permissions.SecurityPermissionFlag> перечисления <xref:System.Security.Permissions.SecurityPermissionFlag> управляют доступом к неуправляемому коду.  Приложение может получить доступ к неуправляемому коду только при наличие разрешения <xref:System.Security.Permissions.SecurityPermissionFlag>.  По умолчанию доступ к неуправляемому коду может получить только локально запущенное приложение.  
  
 Некоторые элементы Windows Forms предоставляют неуправляемый доступ, для которого требуется разрешение <xref:System.Security.Permissions.SecurityPermissionFlag>.  В следующей таблице перечислены элементы пространства имен <xref:System.Windows.Forms>, которым требуется это разрешение.  Дополнительные сведения о разрешениях, которые требуются для элементов, см. в документации по библиотеке классов .NET Framework.  
  
|Компонент|Элемент|  
|---------------|-------------|  
|<xref:System.Windows.Forms.Application>|-   Метод <xref:System.Windows.Forms.Application.AddMessageFilter%2A><br />-   Свойство <xref:System.Windows.Forms.Application.CurrentInputLanguage%2A><br />-   Метод `Exit`<br />-   Метод <xref:System.Windows.Forms.Application.ExitThread%2A><br />-   Событие <xref:System.Windows.Forms.Application.ThreadException>|  
|<xref:System.Windows.Forms.CommonDialog>|-   Метод <xref:System.Windows.Forms.CommonDialog.HookProc%2A><br />-   Метод <xref:System.Windows.Forms.CommonDialog.OwnerWndProc%2A><br />-   Метод <xref:System.Windows.Forms.CommonDialog.Reset%2A><br />-   Метод <xref:System.Windows.Forms.CommonDialog.RunDialog%2A>|  
|<xref:System.Windows.Forms.Control>|-   Метод <xref:System.Windows.Forms.Control.CreateParams%2A><br />-   Метод <xref:System.Windows.Forms.Control.DefWndProc%2A><br />-   Метод <xref:System.Windows.Forms.Control.DestroyHandle%2A><br />-   Метод <xref:System.Windows.Forms.Control.WndProc%2A>|  
|<xref:System.Windows.Forms.Help>|-   Методы <xref:System.Windows.Forms.Help.ShowHelp%2A><br />-   Метод <xref:System.Windows.Forms.Help.ShowHelpIndex%2A>|  
|<xref:System.Windows.Forms.NativeWindow>|-   Класс <xref:System.Windows.Forms.NativeWindow>|  
|<xref:System.Windows.Forms.Screen>|-   Метод <xref:System.Windows.Forms.Screen.FromHandle%2A>|  
|<xref:System.Windows.Forms.SendKeys>|-   Метод <xref:System.Windows.Forms.SendKeys.Send%2A><br />-   Метод <xref:System.Windows.Forms.SendKeys.SendWait%2A>|  
  
 Если приложение не имеет разрешения для вызова неуправляемого кода, необходимо запросить разрешение <xref:System.Security.Permissions.SecurityPermissionFlag> или подумать о других способах реализации этих возможностей; в большинстве случаев в Windows Forms предусмотрен альтернативный управляемый код для функций интерфейса Win32 API.  Если других возможностей не существует и приложение должно иметь доступ к неуправляемому коду, следует повысить уровень разрешений для приложения.  
  
 Разрешение на вызов неуправляемого кода позволяет приложению выполнять практически любые действия.  По этой причине разрешения на вызов неуправляемого кода должны выдаваться только тем приложениям, которые получены из доверенных источников.  Кроме того, в зависимости от приложения, часть функциональных возможностей приложения, которая вызывает неуправляемый код, может быть необязательной или предназначенной для включения только в среде с полным доверием.  Дополнительные сведения о небезопасных разрешениях см. в разделе [Опасные разрешения и администрирование политик](../../../docs/framework/misc/dangerous-permissions-and-policy-administration.md).  Дополнительные сведения о повышении уровня разрешений см. в разделе [NIB: General Security Policy Administration](http://msdn.microsoft.com/ru-ru/5121fe35-f0e3-402c-94ab-4f35b0a87b4b).  
  
## См. также  
 [More Secure File and Data Access in Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)   
 [More Secure Printing in Windows Forms](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)   
 [Security in Windows Forms Overview](../../../docs/framework/winforms/security-in-windows-forms-overview.md)   
 [Windows Forms Security](../../../docs/framework/winforms/windows-forms-security.md)   
 [Защита приложений ClickOnce](../Topic/Securing%20ClickOnce%20Applications.md)