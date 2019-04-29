---
title: 'Как выполнить: Считывание параметров во время выполнения с помощью C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: 8cdc1a79f1ab327ae037cd6a04aa769196405127
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966934"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a>Как выполнить: Считывание параметров во время выполнения с помощью C\#

Параметры области приложения и параметры области пользователя можно считывать во время выполнения с помощью объекта "Свойства". Объект "Свойства" предоставляет все параметры по умолчанию для проекта через элемент Properties.Settings.Default.  
  
## <a name="to-read-settings-at-run-time-with-c"></a>Считывание параметров во время выполнения с помощью C\#
  
Доступ к соответствующему параметру через элемент Properties.Settings.Default. В следующем примере показано, как назначить параметр с именем `myColor` свойству BackColor. Необходимо наличие ранее созданного файла параметров, содержащего параметр с именем `myColor` и типом `System.Drawing.Color`. Сведения о создании файла параметров, см. в разделе [How To: Создание новых параметров во время разработки](how-to-create-a-new-setting-at-design-time.md).  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a>См. также

- [Использование параметров приложения и параметров пользователя](using-application-settings-and-user-settings.md)
- [Практическое руководство. Написание параметров пользователя во время выполнения с помощьюC#](how-to-write-user-settings-at-run-time-with-csharp.md)
- [Общие сведения о параметрах приложений](application-settings-overview.md)
