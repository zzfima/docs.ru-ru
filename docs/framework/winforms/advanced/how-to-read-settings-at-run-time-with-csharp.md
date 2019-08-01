---
title: Как Считывание параметров во время выполнения с помощью C#
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: 6a40718d57fad4041eeea2fded03b7256abbe8d1
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710225"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a>Как Чтение параметров во время выполнения с помощью C\#

Параметры области приложения и параметры области пользователя можно считывать во время выполнения с помощью объекта "Свойства". Объект Properties предоставляет все параметры по умолчанию для проекта с помощью элемента properties. Settings. Default в пространстве имен по умолчанию для проекта, в котором они определены.  
  
## <a name="to-read-settings-at-run-time-with-c"></a>Чтение параметров во время выполнения с помощью C\#
  
Доступ к соответствующему параметру через элемент Properties.Settings.Default. В следующем примере показано, как назначить параметр с именем `myColor` свойству BackColor. Необходимо наличие ранее созданного файла параметров, содержащего параметр с именем `myColor` и типом `System.Drawing.Color`. Сведения о создании файла параметров см. в разделе [как Создайте новый параметр во время](how-to-create-a-new-setting-at-design-time.md)разработки.  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a>См. также

- [Использование параметров приложения и параметров пользователя](using-application-settings-and-user-settings.md)
- [Практическое руководство. Запись параметров пользователя во время выполнения с помощьюC#](how-to-write-user-settings-at-run-time-with-csharp.md)
- [Общие сведения о параметрах приложений](application-settings-overview.md)
