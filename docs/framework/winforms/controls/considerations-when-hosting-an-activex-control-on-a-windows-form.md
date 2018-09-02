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
ms.openlocfilehash: ebf856078d24ef44ca0e04955e0a971de68bb3ce
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43421441"
---
# <a name="considerations-when-hosting-an-activex-control-on-a-windows-form"></a>Вопросы размещения элемента управления ActiveX в форме Windows Forms
Несмотря на то что формы Windows Forms оптимизированы для размещения элементов управления Windows Forms, в формах также можно использовать элементы управления ActiveX. При планировании приложения, использующего элементы управления ActiveX, необходимо учитывать следующие факторы:  
  
-   **Безопасность**. Среда CLR была усовершенствована с точки зрения безопасности доступа для кода. Приложения, использующие Windows Forms, могут выполняться в полностью доверенной среде без каких-либо проблем и в среде с частичным доверием с большинством функциональных возможностей. Элементы управления Windows Forms поддерживают размещение в браузере безо всяких сложностей. Тем не менее элементы управления ActiveX в Windows Forms не могут использовать преимущества этих улучшений безопасности. Запуска элемента управления ActiveX требуются разрешения неуправляемого кода, которые задаются с <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> свойство. Дополнительные сведения о безопасности и разрешениях неуправляемого кода, см. в разделе <xref:System.Security.Permissions.SecurityPermissionAttribute>.  
  
-   **Общая стоимость владения**. Элементы управления ActiveX, добавляемые в форму Windows Forms, развертываются с помощью этой формы полностью, что значительно увеличивает размер создаваемых файлов. Кроме того, для использования элементов управления ActiveX в формах Windows Forms требуется запись в реестр. Таким образом, они более активно вмешиваются в работу компьютера пользователя, чем элементы управления Windows Forms, которые этого не требуют.  
  
    > [!NOTE]
    >  Работа с элементами управления ActiveX требует использования оболочки COM-взаимодействия. Дополнительные сведения см. в разделе [COM-взаимодействие в Visual Basic и Visual C#](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
    > [!NOTE]
    >  Если имя члена элемента управления ActiveX совпадает с именем, определенные в [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], а затем программа импорта элементов управления ActiveX добавит префикс к имени члена **Ctl** при создании <xref:System.Windows.Forms.AxHost> производного класса. Например, если элемент управления ActiveX содержит член с именем **Layout**, в производном от AxHost классе он будет переименован в **CtlLayout**, так как в [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] задано событие **Layout**.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Добавление элементов управления ActiveX в формы Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [Управление доступом для кода](../../../../docs/framework/misc/code-access-security.md)  
 [Сравнение элементов управления и программируемых объектов в разных языках и библиотеках](https://msdn.microsoft.com/library/021f2a1b-8247-4348-a5ad-e1d9ab23004b)  
 [Размещение элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)  
 [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md)
