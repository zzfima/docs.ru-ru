---
title: Практическое руководство. Считывание параметров во время выполнения с помощью C#
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: 8259e2f429718793c01868855651d1000620fae5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-read-settings-at-run-time-with-c"></a>Практическое руководство. Считывание параметров во время выполнения с помощью C# #
Параметры области приложения и параметры области пользователя можно считывать во время выполнения с помощью объекта "Свойства". Объект "Свойства" предоставляет все параметры по умолчанию для проекта через элемент Properties.Settings.Default.  
  
### <a name="to-read-settings-at-run-time-with-c"></a>Считывание параметров во время выполнения с помощью C#  
  
-   Доступ к соответствующему параметру через элемент Properties.Settings.Default. В следующем примере показано, как назначить параметр с именем `myColor` свойству BackColor. Необходимо наличие ранее созданного файла параметров, содержащего параметр с именем `myColor` и типом `System.Drawing.Color`. Сведения о создании файла параметров см. в разделе [How To: создать новый параметр во время разработки](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md).  
  
    ```  
    // C#  
    this.BackColor = Properties.Settings.Default.myColor;  
    ```  
  
## <a name="see-also"></a>См. также  
 [Использование параметров приложения и параметров пользователя](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [Практическое руководство. Написание параметров пользователя во время выполнения с помощью C#](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)  
 [Общие сведения о параметрах приложений](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
