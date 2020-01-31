---
title: Дополнительные вопросы безопасности
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, secure calls to Windows API
- security [Windows Forms]
- security [Windows Forms], calling APIs
- Clipboard [Windows Forms], securing access
ms.assetid: 15abda8b-0527-47c7-aedb-77ab595f2bf1
ms.openlocfilehash: c8d51a57194f1dc536bc4b5d0376987dbfd3b2cf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739818"
---
# <a name="additional-security-considerations-in-windows-forms"></a>Дополнительные вопросы безопасности в формах Windows Forms
.NET Framework параметры безопасности могут привести к тому, что приложение будет выполняться иначе в среде с частичным доверием, чем на локальном компьютере. В .NET Framework ограничен доступ к таким критическим локальным ресурсам, как файловая система, сеть и неуправляемые API, помимо прочего. Параметры безопасности влияют на возможность вызова API Microsoft Windows или других интерфейсов API, которые не могут быть проверены системой безопасности. Безопасность также влияет на другие аспекты приложения, включая доступ к файлам и данным, и вывод на печать. Дополнительные сведения о доступе к файлам и данным в среде с частичным доверием см. в разделе [Более безопасный доступ к файлам и данным в Windows Forms](more-secure-file-and-data-access-in-windows-forms.md). Дополнительные сведения о выводе на печать в среде с частичным доверием см. в разделе [Более безопасная печать в Windows Forms](more-secure-printing-in-windows-forms.md).  
  
 В следующих разделах описывается работа с буфером обмена, выполнение операций с окнами и вызов API Windows из приложений, работающих в среде с частичным доверием.  
  
## <a name="clipboard-access"></a>Доступ к буферу обмена  
 Класс <xref:System.Security.Permissions.UIPermission> управляет доступом к буферу обмена, а соответствующее значение перечисления <xref:System.Security.Permissions.UIPermissionClipboard> указывает уровень доступа. В следующей таблице приведены возможные уровни разрешения.  
  
|Значение UIPermissionClipboard|Описание|  
|---------------------------------|-----------------|  
|<xref:System.Security.Permissions.UIPermissionClipboard.AllClipboard>|Буфер обмена можно использовать без ограничений.|  
|<xref:System.Security.Permissions.UIPermissionClipboard.OwnClipboard>|Буфер обмена можно использовать с некоторыми ограничениями. Возможность размещения данных в буфере обмена (операции с командами копирования и вырезания) не ограничена. Встроенные элементы управления, которые принимают операцию вставки, например текстовое поле, могут принимать данные из буфера обмена, но пользовательские элементы управления не могут программно считывать данные из буфера обмена.|  
|<xref:System.Security.Permissions.UIPermissionClipboard.NoClipboard>|Буфер обмена использовать нельзя.|  
  
 По умолчанию зона локальной интрасети получает <xref:System.Security.Permissions.UIPermissionClipboard.AllClipboard> доступ, а зона Интернета — <xref:System.Security.Permissions.UIPermissionClipboard.OwnClipboard> доступ. Это означает, что приложение может копировать данные в буфер обмена, но не может программно вставлять или считывать данные из буфера обмена. Благодаря таким ограничениям программы, не имеющие полного доверия, не могут считывать содержимое из буфера обмена, скопированное другим приложением. Если приложению требуется полный доступ к буферу обмена, но у вас нет соответствующих разрешений, для приложения необходимо повысить уровень разрешений. Дополнительные сведения о повышении уровня разрешений см. в разделе [Общее администрирование политик безопасности](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100)).  
  
## <a name="window-manipulation"></a>Управление окнами  
 Класс <xref:System.Security.Permissions.UIPermission> также управляет разрешением на выполнение операций с окнами и других действий, связанных с интерфейсом пользователя, а связанное значение перечисления <xref:System.Security.Permissions.UIPermissionWindow> указывает уровень доступа. В следующей таблице приведены возможные уровни разрешения.  
  
 По умолчанию зона локальной интрасети получает <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> доступ, а зона Интернета — <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> доступ. Это означает, что в зоне Интернета приложение может выполнять большинство операций с окнами и пользовательским интерфейсом, но внешний вид окна будет изменяться. В измененном окне при первом запуске отображается всплывающее уведомление. В таком окне также изменен заголовок, а в строке заголовка должна быть кнопка "Закрыть". Всплывающее уведомление и строка заголовка информируют пользователя приложения о том, что данное приложение выполняется в режиме частичного доверия.  
  
|Значение UIPermissionWindow|Описание|  
|------------------------------|-----------------|  
|<xref:System.Security.Permissions.UIPermissionWindow.AllWindows>|Пользователи могут использовать все окна и события пользовательского ввода без каких-либо ограничений.|  
|<xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows>|Пользователи могут использовать для рисования только более безопасные окна верхнего уровня и дочерние окна, а также события пользовательского ввода для пользовательского интерфейса в таких окнах и дочерних окнах. Такие более безопасные окна имеют специальные метки, а также ограничения на минимальный и максимальный размер. Ограничения предотвращают потенциально опасные атаки с подменой, такие как имитация экранов входа в систему или системных настольных систем, и ограничение программного доступа к родительским окнам, интерфейсам API, связанным с фокусом, и использованию элемента управления <xref:System.Windows.Forms.ToolTip>|  
|<xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows>|Пользователи могут использовать для рисования только более безопасные дочерние окна, а также события пользовательского ввода для пользовательского интерфейса в таких дочерних окнах. Примером такого более безопасного дочернего окна является элемент управления, отображаемый в браузере.|  
|<xref:System.Security.Permissions.UIPermissionWindow.NoWindows>|Пользователи не могут использовать никакие окна и события пользовательского интерфейса. Пользовательский интерфейс использовать нельзя.|  
  
 Каждый уровень разрешений, определяемый перечислением <xref:System.Security.Permissions.UIPermissionWindow>, допускает меньше действий, чем уровень выше. В следующих таблицах указываются действия, ограниченные <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> и <xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows> значениями. Точные разрешения, необходимые для каждого члена, представлены в справочном разделе для этого члена в документации по библиотеке классов .NET Framework.  
  
 <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> разрешения ограничивают действия, перечисленные в следующей таблице.  
  
|Компонент|Ограниченные действия|  
|---------------|------------------------|  
|<xref:System.Windows.Forms.Application>|— Задание значения для свойства <xref:System.Windows.Forms.Application.SafeTopLevelCaptionFormat%2A>.|  
|<xref:System.Windows.Forms.Control>|— Получение свойства <xref:System.Windows.Forms.Control.Parent%2A>.<br />— Задание значения для свойства `Region`.<br />— Вызов метода <xref:System.Windows.Forms.Control.FindForm%2A>, <xref:System.Windows.Forms.Control.Focus%2A>, <xref:System.Windows.Forms.Control.FromChildHandle%2A> и <xref:System.Windows.Forms.Control.FromHandle%2A>, <xref:System.Windows.Forms.Control.PreProcessMessage%2A>, <xref:System.Windows.Forms.Control.ReflectMessage%2A>или <xref:System.Windows.Forms.Control.SetTopLevel%2A>.<br />— Вызов метода <xref:System.Windows.Forms.Control.GetChildAtPoint%2A>, если возвращаемый элемент управления не является дочерним элементом вызывающего элемента управления.<br />— Изменение фокуса элемента управления в контейнерном элементе управления.|  
|<xref:System.Windows.Forms.Cursor>|— Задание значения для свойства <xref:System.Windows.Forms.Cursor.Clip%2A>.<br />— Вызов метода <xref:System.Windows.Forms.Control.Hide%2A>.|  
|<xref:System.Windows.Forms.DataGrid>|— Вызов метода <xref:System.Windows.Forms.ContainerControl.ProcessTabKey%2A>.|  
|<xref:System.Windows.Forms.Form>|— Получение свойства <xref:System.Windows.Forms.Form.ActiveForm%2A> или <xref:System.Windows.Forms.Form.MdiParent%2A>.<br />— Задание свойства <xref:System.Windows.Forms.Form.ControlBox%2A>, <xref:System.Windows.Forms.Form.ShowInTaskbar%2A>или <xref:System.Windows.Forms.Form.TopMost%2A>.<br />— Установка свойства <xref:System.Windows.Forms.Form.Opacity%2A> ниже 50%.<br />— Установка свойства <xref:System.Windows.Forms.Form.WindowState%2A> в <xref:System.Windows.Forms.FormWindowState.Minimized> программным способом.<br />— Вызов метода <xref:System.Windows.Forms.Form.Activate%2A>.<br />— С помощью значений перечисления <xref:System.Windows.Forms.FormBorderStyle.None>, <xref:System.Windows.Forms.FormBorderStyle.FixedToolWindow>и <xref:System.Windows.Forms.FormBorderStyle.SizableToolWindow><xref:System.Windows.Forms.FormBorderStyle>.|  
|<xref:System.Windows.Forms.NotifyIcon>|— Использование компонента <xref:System.Windows.Forms.NotifyIcon> полностью ограничено.|  
  
 <xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows> значение позволяет ограничить действия, перечисленные в следующей таблице, в дополнение к ограничениям, накладываемым <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows>ным значением.  
  
|Компонент|Ограниченные действия|  
|---------------|------------------------|  
|<xref:System.Windows.Forms.CommonDialog>|— Отображение диалогового окна, производного от класса <xref:System.Windows.Forms.CommonDialog>.|  
|<xref:System.Windows.Forms.Control>|— Вызов метода <xref:System.Windows.Forms.Control.CreateGraphics%2A>.<br />— Задание значения для свойства <xref:System.Windows.Forms.Control.Cursor%2A>.|  
|<xref:System.Windows.Forms.Control.Cursor%2A>|— Задание значения для свойства <xref:System.Windows.Forms.Cursor.Current%2A>.|  
|<xref:System.Windows.Forms.MessageBox>|— Вызов метода <xref:System.Windows.Forms.Form.Show%2A>.|  
  
### <a name="hosting-third-party-controls"></a>Размещение элементов управления сторонних производителей  
 Если ваши формы размещают элементы управления сторонних производителей, могут возникать другие операции управления окнами. Сторонние элементы управления — это любые пользовательские <xref:System.Windows.Forms.UserControl>, которые вы не разработали и откомпилированы самостоятельно. Несмотря на то, что вариантом размещения воспользоваться довольно сложно, теоретически элемент управления стороннего производителя может расширить свою поверхность отрисовки и полностью занять область вашей формы. Затем такой элемент управления может сымитировать важное диалоговое окно и запросить у ваших пользователей такие сведения, как сочетание имени пользователя и пароля или номера банковских счетов.  
  
 Чтобы ограничить такой потенциальный риск, используйте элементы управления только доверенных сторонних производителей. Если вы используете элементы управления стороннего производителя, загруженные из непроверяемого источника, рекомендуем просмотреть исходный код на предмет наличия потенциальной уязвимости. Убедившись, что источник не является вредоносным, скомпилируйте сборку самостоятельно и проверьте, соответствует ли исходный код сборке.  
  
## <a name="windows-api-calls"></a>Вызовы Windows API  
 Если проект приложения требует вызова функции из Windows API, вы обращаетесь к неуправляемому коду. В этом случае действия кода для окна или операционной системы не могут быть определены при работе с вызовами или значениями API Windows. Класс <xref:System.Security.Permissions.SecurityPermission> и <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> значение элемента управления перечислением <xref:System.Security.Permissions.SecurityPermissionFlag> доступ к неуправляемому коду. Приложение может обращаться к неуправляемому коду только в том случае, если ему предоставлено разрешение <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>. По умолчанию вызывать неуправляемый код могут только приложения, которые выполняются локально.  
  
 Некоторые Windows Forms члены предоставляют неуправляемый доступ, для которого требуется разрешение <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>. В следующей таблице перечислены элементы пространства имен <xref:System.Windows.Forms>, для которых требуется разрешение. Дополнительные сведения о разрешениях, требуемых для элемента, см. в разделе документации по библиотеке классов .NET Framework.  
  
|Компонент|Член|  
|---------------|------------|  
|<xref:System.Windows.Forms.Application>|Метод -   <xref:System.Windows.Forms.Application.AddMessageFilter%2A><br />-   <xref:System.Windows.Forms.Application.CurrentInputLanguage%2A> свойство<br />Метод -   `Exit`<br />Метод -   <xref:System.Windows.Forms.Application.ExitThread%2A><br />событие -   <xref:System.Windows.Forms.Application.ThreadException>|  
|<xref:System.Windows.Forms.CommonDialog>|Метод -   <xref:System.Windows.Forms.CommonDialog.HookProc%2A><br />-   <xref:System.Windows.Forms.CommonDialog.OwnerWndProc%2A>\ метод<br />Метод -   <xref:System.Windows.Forms.CommonDialog.Reset%2A><br />Метод -   <xref:System.Windows.Forms.CommonDialog.RunDialog%2A>|  
|<xref:System.Windows.Forms.Control>|Метод -   <xref:System.Windows.Forms.Control.CreateParams%2A><br />Метод -   <xref:System.Windows.Forms.Control.DefWndProc%2A><br />Метод -   <xref:System.Windows.Forms.Control.DestroyHandle%2A><br />Метод -   <xref:System.Windows.Forms.Control.WndProc%2A>|  
|<xref:System.Windows.Forms.Help>|методы <xref:System.Windows.Forms.Help.ShowHelp%2A> -   <br />Метод -   <xref:System.Windows.Forms.Help.ShowHelpIndex%2A>|  
|<xref:System.Windows.Forms.NativeWindow>|класс -   <xref:System.Windows.Forms.NativeWindow>|  
|<xref:System.Windows.Forms.Screen>|Метод -   <xref:System.Windows.Forms.Screen.FromHandle%2A>|  
|<xref:System.Windows.Forms.SendKeys>|Метод -   <xref:System.Windows.Forms.SendKeys.Send%2A><br />Метод -   <xref:System.Windows.Forms.SendKeys.SendWait%2A>|  
  
 Если приложение не имеет разрешения на вызов неуправляемого кода, приложение должно запросить <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> разрешение, либо следует рассмотреть альтернативные способы реализации функций. во многих случаях Windows Forms предоставляет управляемую альтернативу функциям Windows API. Если альтернативного способа нет, а приложению необходимо получать доступ к неуправляемому коду, повысьте уровень разрешений для такого приложения.  
  
 Благодаря разрешению на вызов неуправляемого кода приложение может выполнять практически любые действия. Следовательно, разрешение на вызов неуправляемого кода должно предоставляться только приложениям из доверенного источника. Кроме того, в зависимости от приложения, часть функциональных возможностей приложения, вызывающих неуправляемый код, может быть необязательной или использоваться только в среде с полным доверием. Дополнительные сведения об опасных разрешениях см. в разделе [Опасные разрешения и администрирование политик](../misc/dangerous-permissions-and-policy-administration.md). Дополнительные сведения о повышении уровня разрешений см. в разделе [Общее администрирование политик безопасности](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100)).  
  
## <a name="see-also"></a>См. также:

- [Более безопасный доступ к файлам и данным в Windows Forms](more-secure-file-and-data-access-in-windows-forms.md)
- [Более безопасная печать в Windows Forms](more-secure-printing-in-windows-forms.md)
- [Общие сведения о безопасности в Windows Forms](security-in-windows-forms-overview.md)
- [Безопасность Windows Forms](windows-forms-security.md)
- [Защита приложений ClickOnce](/visualstudio/deployment/securing-clickonce-applications)
