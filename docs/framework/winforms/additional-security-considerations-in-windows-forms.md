---
title: Дополнительные вопросы безопасности в формах Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, secure calls to Windows API
- security [Windows Forms]
- security [Windows Forms], calling APIs
- Clipboard [Windows Forms], securing access
ms.assetid: 15abda8b-0527-47c7-aedb-77ab595f2bf1
ms.openlocfilehash: a1d8606eb972a6e3bea52f6230cb893a4bbb5aac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="additional-security-considerations-in-windows-forms"></a>Дополнительные вопросы безопасности в формах Windows Forms
Приложение может работать по-разному в среде с частичным доверием и на локальном компьютере из-за параметров безопасности [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]. [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] ограничивает доступ, помимо прочего, к таким важным локальным ресурсам, как файловая система, сеть и неуправляемые API. Параметры безопасности влияют на возможность вызова интерфейса Microsoft Win32 API или других интерфейсов API, которые не могут быть проверены системой безопасности. Безопасность также влияет на другие аспекты приложения, включая доступ к файлам и данным, и вывод на печать. Дополнительные сведения о доступе к файлам и данным в среде с частичным доверием см. в разделе [Более безопасный доступ к файлам и данным в Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md). Дополнительные сведения о выводе на печать в среде с частичным доверием см. в разделе [Более безопасная печать в Windows Forms](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md).  
  
 В следующих разделах описывается работа с буфером обмена, управление окнами и вызов Win32 API из приложений, работающих в среде с частичным доверием.  
  
## <a name="clipboard-access"></a>Доступ к буферу обмена  
 <xref:System.Security.Permissions.UIPermission> Класс управляет доступом к буфера обмена, а также <xref:System.Security.Permissions.UIPermissionClipboard> значение перечисления указывает уровень доступа. В следующей таблице приведены возможные уровни разрешения.  
  
|Значение UIPermissionClipboard|Описание|  
|---------------------------------|-----------------|  
|<xref:System.Security.Permissions.UIPermissionClipboard.AllClipboard>|Буфер обмена можно использовать без ограничений.|  
|<xref:System.Security.Permissions.UIPermissionClipboard.OwnClipboard>|Буфер обмена можно использовать с некоторыми ограничениями. Возможность размещения данных в буфере обмена (операции с командами копирования и вырезания) не ограничена. Встроенные элементы управления, которые принимают операцию вставки, например текстовое поле, могут принимать данные из буфера обмена, но пользовательские элементы управления не могут программно считывать данные из буфера обмена.|  
|<xref:System.Security.Permissions.UIPermissionClipboard.NoClipboard>|Буфер обмена использовать нельзя.|  
  
 По умолчанию зона локальной интрасети получает <xref:System.Security.Permissions.UIPermissionClipboard.AllClipboard> доступа и зона Интернета получает <xref:System.Security.Permissions.UIPermissionClipboard.OwnClipboard> доступа. Это означает, что приложение может копировать данные в буфер обмена, но не может программно вставлять или считывать данные из буфера обмена. Благодаря таким ограничениям программы, не имеющие полного доверия, не могут считывать содержимое из буфера обмена, скопированное другим приложением. Если приложению требуется полный доступ к буферу обмена, но у вас нет соответствующих разрешений, для приложения необходимо повысить уровень разрешений. Дополнительные сведения о повышении уровня разрешений см. в разделе [Общее администрирование политик безопасности](http://msdn.microsoft.com/library/5121fe35-f0e3-402c-94ab-4f35b0a87b4b).  
  
## <a name="window-manipulation"></a>Управление окнами  
 <xref:System.Security.Permissions.UIPermission> Класс также управляет разрешениями на выполнение с окнами и другие действия, связанные с Пользовательским интерфейсом, а также <xref:System.Security.Permissions.UIPermissionWindow> значение перечисления указывает уровень доступа. В следующей таблице приведены возможные уровни разрешения.  
  
 По умолчанию зона локальной интрасети получает <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> доступа и зона Интернета получает <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> доступа. Это означает, что в зоне Интернета приложение может выполнять большинство операций с окнами и пользовательским интерфейсом, но внешний вид окна будет изменяться. В измененном окне при первом запуске отображается всплывающее уведомление. В таком окне также изменен заголовок, а в строке заголовка должна быть кнопка "Закрыть". Всплывающее уведомление и строка заголовка информируют пользователя приложения о том, что данное приложение выполняется в режиме частичного доверия.  
  
|Значение UIPermissionWindow|Описание|  
|------------------------------|-----------------|  
|<xref:System.Security.Permissions.UIPermissionWindow.AllWindows>|Пользователи могут использовать все окна и события пользовательского ввода без каких-либо ограничений.|  
|<xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows>|Пользователи могут использовать для рисования только более безопасные окна верхнего уровня и дочерние окна, а также события пользовательского ввода для пользовательского интерфейса в таких окнах и дочерних окнах. Такие более безопасные окна имеют специальные метки, а также ограничения на минимальный и максимальный размер. Эти ограничения предотвращают атаки спуфинга потенциально опасной, такие как имитация экрана входа в систему или рабочего стола системы и не программный доступ к родительским windows API, связанные с фокусом и использование <xref:System.Windows.Forms.ToolTip> элемента управления|  
|<xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows>|Пользователи могут использовать для рисования только более безопасные дочерние окна, а также события пользовательского ввода для пользовательского интерфейса в таких дочерних окнах. Примером такого более безопасного дочернего окна является элемент управления, отображаемый в браузере.|  
|<xref:System.Security.Permissions.UIPermissionWindow.NoWindows>|Пользователи не могут использовать никакие окна и события пользовательского интерфейса. Пользовательский интерфейс использовать нельзя.|  
  
 Каждый уровень разрешений, определенный <xref:System.Security.Permissions.UIPermissionWindow> перечисления позволяет меньше действий, чем предыдущий уровень. В следующих таблицах содержатся действия, которые ограничены <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> и <xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows> значения. Точные разрешения, необходимые для каждого члена, представлены в справочном разделе для этого члена в документации по библиотеке классов .NET Framework.  
  
 <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> разрешение ограничивает действия, приведенные в следующей таблице.  
  
|Компонент|Ограниченные действия|  
|---------------|------------------------|  
|<xref:System.Windows.Forms.Application>|— Задание значения для свойства <xref:System.Windows.Forms.Application.SafeTopLevelCaptionFormat%2A>.|  
|<xref:System.Windows.Forms.Control>|-Получение <xref:System.Windows.Forms.Control.Parent%2A> свойство.<br />— Задание значения для свойства `Region`.<br />-Вызов <xref:System.Windows.Forms.Control.FindForm%2A> , <xref:System.Windows.Forms.Control.Focus%2A>, <xref:System.Windows.Forms.Control.FromChildHandle%2A> и <xref:System.Windows.Forms.Control.FromHandle%2A>, <xref:System.Windows.Forms.Control.PreProcessMessage%2A>, <xref:System.Windows.Forms.Control.ReflectMessage%2A>, или <xref:System.Windows.Forms.Control.SetTopLevel%2A> метод.<br />-Вызов <xref:System.Windows.Forms.Control.GetChildAtPoint%2A> метод, если возвращенный элемент управления не является дочерним вызывающего элемента управления.<br />— Изменение фокуса элемента управления в контейнерном элементе управления.|  
|<xref:System.Windows.Forms.Cursor>|— Задание значения для свойства <xref:System.Windows.Forms.Cursor.Clip%2A>.<br />-Вызов <xref:System.Windows.Forms.Control.Hide%2A> метод.|  
|<xref:System.Windows.Forms.DataGrid>|-Вызов <xref:System.Windows.Forms.ContainerControl.ProcessTabKey%2A> метод.|  
|<xref:System.Windows.Forms.Form>|-Получение <xref:System.Windows.Forms.Form.ActiveForm%2A> или <xref:System.Windows.Forms.Form.MdiParent%2A> свойства.<br />-Параметр <xref:System.Windows.Forms.Form.ControlBox%2A>, <xref:System.Windows.Forms.Form.ShowInTaskbar%2A>, или <xref:System.Windows.Forms.Form.TopMost%2A> свойства.<br />-Параметр <xref:System.Windows.Forms.Form.Opacity%2A> свойство ниже 50%.<br />-Параметр <xref:System.Windows.Forms.Form.WindowState%2A> свойства <xref:System.Windows.Forms.FormWindowState.Minimized> программными средствами.<br />-Вызов <xref:System.Windows.Forms.Form.Activate%2A> метод.<br />-С помощью <xref:System.Windows.Forms.FormBorderStyle.None>, <xref:System.Windows.Forms.FormBorderStyle.FixedToolWindow>, и <xref:System.Windows.Forms.FormBorderStyle.SizableToolWindow> <xref:System.Windows.Forms.FormBorderStyle> значений перечисления.|  
|<xref:System.Windows.Forms.NotifyIcon>|-С помощью <xref:System.Windows.Forms.NotifyIcon> компонент является полностью запрещено.|  
  
 <xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows> Ограничивает действия, перечисленные в следующей таблице, кроме ограничения, налагаемые по <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> значение.  
  
|Компонент|Ограниченные действия|  
|---------------|------------------------|  
|<xref:System.Windows.Forms.CommonDialog>|-Отображение диалогового окна производным от <xref:System.Windows.Forms.CommonDialog> класса.|  
|<xref:System.Windows.Forms.Control>|-Вызов <xref:System.Windows.Forms.Control.CreateGraphics%2A> метод.<br />— Задание значения для свойства <xref:System.Windows.Forms.Control.Cursor%2A>.|  
|<xref:System.Windows.Forms.Control.Cursor%2A>|— Задание значения для свойства <xref:System.Windows.Forms.Cursor.Current%2A>.|  
|<xref:System.Windows.Forms.MessageBox>|-Вызов <xref:System.Windows.Forms.Form.Show%2A> метод.|  
  
### <a name="hosting-third-party-controls"></a>Размещение элементов управления сторонних производителей  
 Если ваши формы размещают элементы управления сторонних производителей, могут возникать другие операции управления окнами. Сторонний элемент управления является пользовательской <xref:System.Windows.Forms.UserControl> не имеют разработки и компиляции самостоятельно. Несмотря на то, что вариантом размещения воспользоваться довольно сложно, теоретически элемент управления стороннего производителя может расширить свою поверхность отрисовки и полностью занять область вашей формы. Затем такой элемент управления может сымитировать важное диалоговое окно и запросить у ваших пользователей такие сведения, как сочетание имени пользователя и пароля или номера банковских счетов.  
  
 Чтобы ограничить такой потенциальный риск, используйте элементы управления только доверенных сторонних производителей. Если вы используете элементы управления стороннего производителя, загруженные из непроверяемого источника, рекомендуем просмотреть исходный код на предмет наличия потенциальной уязвимости. Убедившись, что источник не является вредоносным, скомпилируйте сборку самостоятельно и проверьте, соответствует ли исходный код сборке.  
  
## <a name="win32-api-calls"></a>Вызовы API Win32  
 Если при разработке приложения требуется вызов функции из интерфейса API Win32, осуществляется доступ к неуправляемому коду. В этом случае при работе с вызовами Win32 API или значениями действия кода с окном или операционной системой определить невозможно. <xref:System.Security.Permissions.SecurityPermission> Класса и <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> значение <xref:System.Security.Permissions.SecurityPermissionFlag> перечисления контроль доступа к неуправляемому коду. Приложение может доступ к неуправляемому коду, только в том случае, если оно предоставлено <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> разрешение. По умолчанию вызывать неуправляемый код могут только приложения, которые выполняются локально.  
  
 Некоторые элементы Windows Forms предоставляют неуправляемый доступ, для которого требуется <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> разрешение. В следующей таблице перечислены элементы <xref:System.Windows.Forms> пространства имен, которым требуется это разрешение. Дополнительные сведения о разрешениях, требуемых для элемента, см. в разделе документации по библиотеке классов .NET Framework.  
  
|Компонент|Член|  
|---------------|------------|  
|<xref:System.Windows.Forms.Application>|Метод -   <xref:System.Windows.Forms.Application.AddMessageFilter%2A><br />-   <xref:System.Windows.Forms.Application.CurrentInputLanguage%2A> Свойство<br />Метод -   `Exit`<br />Метод -   <xref:System.Windows.Forms.Application.ExitThread%2A><br />-   <xref:System.Windows.Forms.Application.ThreadException> Событие|  
|<xref:System.Windows.Forms.CommonDialog>|Метод -   <xref:System.Windows.Forms.CommonDialog.HookProc%2A><br />-   <xref:System.Windows.Forms.CommonDialog.OwnerWndProc%2A>\ метод<br />Метод -   <xref:System.Windows.Forms.CommonDialog.Reset%2A><br />Метод -   <xref:System.Windows.Forms.CommonDialog.RunDialog%2A>|  
|<xref:System.Windows.Forms.Control>|Метод -   <xref:System.Windows.Forms.Control.CreateParams%2A><br />Метод -   <xref:System.Windows.Forms.Control.DefWndProc%2A><br />Метод -   <xref:System.Windows.Forms.Control.DestroyHandle%2A><br />Метод -   <xref:System.Windows.Forms.Control.WndProc%2A>|  
|<xref:System.Windows.Forms.Help>|-   <xref:System.Windows.Forms.Help.ShowHelp%2A> Методы<br />Метод -   <xref:System.Windows.Forms.Help.ShowHelpIndex%2A>|  
|<xref:System.Windows.Forms.NativeWindow>|-   <xref:System.Windows.Forms.NativeWindow> Класс|  
|<xref:System.Windows.Forms.Screen>|Метод -   <xref:System.Windows.Forms.Screen.FromHandle%2A>|  
|<xref:System.Windows.Forms.SendKeys>|Метод -   <xref:System.Windows.Forms.SendKeys.Send%2A><br />Метод -   <xref:System.Windows.Forms.SendKeys.SendWait%2A>|  
  
 Если у приложения отсутствует разрешение на вызов неуправляемого кода, приложение должно запросить <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> разрешение, или необходимо учитывать альтернативные способы реализации этих возможностей; во многих случаях Windows Forms предоставляет управляемую альтернативу Win32 API функции. Если альтернативного способа нет, а приложению необходимо получать доступ к неуправляемому коду, повысьте уровень разрешений для такого приложения.  
  
 Благодаря разрешению на вызов неуправляемого кода приложение может выполнять практически любые действия. Следовательно, разрешение на вызов неуправляемого кода должно предоставляться только приложениям из доверенного источника. Кроме того, в зависимости от приложения, часть функциональных возможностей приложения, вызывающих неуправляемый код, может быть необязательной или использоваться только в среде с полным доверием. Дополнительные сведения об опасных разрешениях см. в разделе [Опасные разрешения и администрирование политик](../../../docs/framework/misc/dangerous-permissions-and-policy-administration.md). Дополнительные сведения о повышении уровня разрешений см. в разделе [NIB. Общее администрирование политик безопасности](http://msdn.microsoft.com/library/5121fe35-f0e3-402c-94ab-4f35b0a87b4b).  
  
## <a name="see-also"></a>См. также  
 [Более безопасный доступ к файлам и данным в Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 [Более безопасная печать в Windows Forms](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)  
 [Общие сведения о безопасности в Windows Forms](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 [Безопасность Windows Forms](../../../docs/framework/winforms/windows-forms-security.md)  
 [Защита приложений ClickOnce](/visualstudio/deployment/securing-clickonce-applications)
