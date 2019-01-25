---
title: 'Как выполнить: Считывание параметров во время выполнения с помощьюC#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: d798b40e5e337ea7652c8e82cb7fa860a87528b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521755"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a>Как выполнить: Считывание параметров во время выполнения с помощьюC# #
Параметры области приложения и параметры области пользователя можно считывать во время выполнения с помощью объекта "Свойства". Объект "Свойства" предоставляет все параметры по умолчанию для проекта через элемент Properties.Settings.Default.  
  
### <a name="to-read-settings-at-run-time-with-c"></a>Считывание параметров во время выполнения с помощью C#  
  
-   Доступ к соответствующему параметру через элемент Properties.Settings.Default. В следующем примере показано, как назначить параметр с именем `myColor` свойству BackColor. Необходимо наличие ранее созданного файла параметров, содержащего параметр с именем `myColor` и типом `System.Drawing.Color`. Сведения о создании файла параметров, см. в разделе [How To: Создание новых параметров во время разработки](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md).  
  
    ```  
    // C#  
    this.BackColor = Properties.Settings.Default.myColor;  
    ```  
  
## <a name="see-also"></a>См. также
- [Использование параметров приложения и параметров пользователя](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)
- [Практическое руководство. Написание параметров пользователя во время выполнения с помощьюC#](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)
- [Общие сведения о параметрах приложений](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
