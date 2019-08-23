---
title: Вопросы размещения элемента управления ActiveX в форме Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- ActiveX controls [Windows Forms], hosting
- Windows Forms, ActiveX controls
- Windows Forms, hosting ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 2509302d-a74e-484f-9890-2acdbfa67a68
ms.openlocfilehash: 0b95bab20299b966b9f3c6e6ce089a641670f974
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933417"
---
# <a name="considerations-when-hosting-an-activex-control-on-a-windows-form"></a>Вопросы размещения элемента управления ActiveX в форме Windows Forms
Несмотря на то что формы Windows Forms оптимизированы для размещения элементов управления Windows Forms, в формах также можно использовать элементы управления ActiveX. При планировании приложения, использующего элементы управления ActiveX, необходимо учитывать следующие факторы:  
  
- **Безопасность**. Среда CLR была усовершенствована с точки зрения безопасности доступа для кода. Приложения, использующие Windows Forms, могут выполняться в полностью доверенной среде без каких-либо проблем и в среде с частичным доверием с большинством функциональных возможностей. Элементы управления Windows Forms поддерживают размещение в браузере безо всяких сложностей. Тем не менее элементы управления ActiveX в Windows Forms не могут использовать преимущества этих улучшений безопасности. Для запуска элемента управления ActiveX требуется разрешение неуправляемого кода, которое задается <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> свойством. Дополнительные сведения о разрешениях безопасности и неуправляемого кода см <xref:System.Security.Permissions.SecurityPermissionAttribute>. в разделе.  
  
- **Общая стоимость владения**. Элементы управления ActiveX, добавляемые в форму Windows Forms, развертываются с помощью этой формы полностью, что значительно увеличивает размер создаваемых файлов. Кроме того, для использования элементов управления ActiveX в формах Windows Forms требуется запись в реестр. Таким образом, они более активно вмешиваются в работу компьютера пользователя, чем элементы управления Windows Forms, которые этого не требуют.  
  
    > [!NOTE]
    > Работа с элементами управления ActiveX требует использования оболочки COM-взаимодействия. Дополнительные сведения см. в разделе [COM-взаимодействие в Visual Basic и Visual C#](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
    > [!NOTE]
    > Если имя элемента элемента управления ActiveX соответствует имени, определенному в .NET Framework, программа импорта элементов управления ActiveX будет добавлять к имени члена **список CTL** при создании <xref:System.Windows.Forms.AxHost> производного класса. Например, если элемент управления ActiveX имеет член с именем **Layout**, он переименовывается в **CtlLayout** в классе, производном от AxHost, так как событие **Layout** определено в .NET Framework.  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Добавление элементов управления ActiveX в Windows Forms](how-to-add-activex-controls-to-windows-forms.md)
- [Управление доступом для кода](../../misc/code-access-security.md)
- [Сравнение элементов управления и программируемых объектов в разных языках и библиотеках](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [Размещение элементов управления в формах Windows Forms](putting-controls-on-windows-forms.md)
- [Элементы управления Windows Forms](index.md)
