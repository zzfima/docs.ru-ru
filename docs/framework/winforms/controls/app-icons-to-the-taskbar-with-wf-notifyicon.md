---
title: Добавление значков приложений на панель задач с компонентом NotifyIcon
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TrayIcon
helpviewer_keywords:
- status area icons
- icons [Windows Forms], adding to taskbar
- NotifyIcon component
- taskbar [Windows Forms], adding icons
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
ms.openlocfilehash: 46b50ecaabe75dba08fea922d7b5639031692269
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746244"
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a>Практическое руководство. Добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms

Компонент Windows Forms <xref:System.Windows.Forms.NotifyIcon> отображает один значок в области уведомлений о состоянии панели задач. Чтобы в области состояния отображалось несколько значков, в форме необходимо несколько <xref:System.Windows.Forms.NotifyIcon> компонентов. Чтобы задать значок, отображаемый для элемента управления, используйте свойство <xref:System.Windows.Forms.NotifyIcon.Icon%2A>. Можно также написать код в обработчике <xref:System.Windows.Forms.NotifyIcon.DoubleClick> событий, чтобы что-то происходит при двойном щелчке значка пользователем. Например, можно открыть диалоговое окно, чтобы пользователь мог настроить фоновый процесс, представленный значком.

> [!NOTE]
> Компонент <xref:System.Windows.Forms.NotifyIcon> используется только в целях уведомления, чтобы предупредить пользователей о том, что произошло действие или событие, либо изменилось состояние некоторой сортировки. Для стандартного взаимодействия с приложениями следует использовать меню, панели инструментов и другие элементы пользовательского интерфейса.

### <a name="to-set-the-icon"></a>Установка значка

1. Присвойте значение свойству <xref:System.Windows.Forms.NotifyIcon.Icon%2A>. Значение должно иметь тип `System.Drawing.Icon` и может быть загружено из файла ICO. Файл значка можно указать в коде или нажав кнопку с многоточием (![многоточием (...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством <xref:System.Windows.Forms.NotifyIcon.Icon%2A> в окне " **Свойства** ", а затем выбрать файл в появившемся **диалоговом** окне.

2. Установите свойство <xref:System.Windows.Forms.NotifyIcon.Visible%2A> в значение `true`.

3. Задайте для свойства <xref:System.Windows.Forms.NotifyIcon.Text%2A> соответствующую строку подсказки.

     В следующем примере кода путь, заданный для расположения значка, — это папка **Мои документы** . Это расположение используется, поскольку можно предположить, что большинство компьютеров, работающих под управлением операционной системы Windows, будут содержать эту папку. Выбор этого расположения также позволяет пользователям с минимальными уровнями доступа к системе безопасно запускать приложение. В следующем примере требуется форма с уже добавленным элементом управления <xref:System.Windows.Forms.NotifyIcon>. Также требуется файл значка с именем `Icon.ico`.

    ```vb
    ' You should replace the bold icon in the sample below
    ' with an icon of your own choosing.
    NotifyIcon1.Icon = New _
       System.Drawing.Icon(System.Environment.GetFolderPath _
       (System.Environment.SpecialFolder.Personal) _
       & "\Icon.ico")
    NotifyIcon1.Visible = True
    NotifyIcon1.Text = "Antivirus program"
    ```

    ```csharp
    // You should replace the bold icon in the sample below
    // with an icon of your own choosing.
    // Note the escape character used (@) when specifying the path.
    notifyIcon1.Icon =
       new System.Drawing.Icon (System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.Personal)
       + @"\Icon.ico");
    notifyIcon1.Visible = true;
    notifyIcon1.Text = "Antivirus program";
    ```

    ```cpp
    // You should replace the bold icon in the sample below
    // with an icon of your own choosing.
    notifyIcon1->Icon = gcnew
       System::Drawing::Icon(String::Concat
       (System::Environment::GetFolderPath
       (System::Environment::SpecialFolder::Personal),
       "\\Icon.ico"));
    notifyIcon1->Visible = true;
    notifyIcon1->Text = "Antivirus program";
    ```

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [Практическое руководство. Связывание контекстного меню с компонентом NotifyIcon в Windows Forms](how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)
- [Компонент NotifyIcon](notifyicon-component-windows-forms.md)
- [Общие сведения о компоненте управления NotifyIcon](notifyicon-component-overview-windows-forms.md)
