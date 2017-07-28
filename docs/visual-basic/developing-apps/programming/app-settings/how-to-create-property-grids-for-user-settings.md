---
title: "Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My.Settings object, creating property grids for user settings
- user settings, creating property grids
- property grids, creating for user settings
- property grids
ms.assetid: b0bc737e-50d1-43d1-a6df-268db6e6f91c
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 533492c030188307f1596b24f1c2fa81940ebfe7
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-create-property-grids-for-user-settings-in-visual-basic"></a>Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic
Вы можете создать таблицу свойств для параметров пользователя, заполнив элемент управления <xref:System.Windows.Forms.PropertyGrid> свойствами параметров пользователей для объекта `My.Settings`.  
  
> [!NOTE]
>  Для надлежащего выполнения этого примера для приложения необходимо настроить пользовательские параметры. Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet).  
  
 Объект `My.Settings` представляет каждый параметр в виде свойства. Имя свойства совпадает с именем параметра, а тип свойства совпадает с типом параметра. **Область** параметра определяет, доступно ли свойство только для чтения. Свойство для параметра с областью **Приложение** доступно только для чтения, а свойство для параметра с областью **Пользователь** доступно для чтения или записи. Дополнительные сведения см. в разделе [Объект My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
>  Невозможно изменить или сохранить значения параметров области определения приложения во время выполнения. Параметры области определения приложения можно изменить только при создании приложения (с помощью **конструктора проектов**) или путем изменения файла конфигурации приложения. Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet).  
  
 В этом примере элемент управления <xref:System.Windows.Forms.PropertyGrid> используется для доступа к свойствам параметров пользователей объекта `My.Settings`. По умолчанию <xref:System.Windows.Forms.PropertyGrid> отображает все свойства объекта `My.Settings`. Однако свойства параметров пользователей имеют атрибут <xref:System.Configuration.UserScopedSettingAttribute>. В данном примере для свойства <xref:System.Windows.Forms.PropertyGrid.BrowsableAttributes%2A> объекта <xref:System.Windows.Forms.PropertyGrid> устанавливается значение <xref:System.Configuration.UserScopedSettingAttribute>, чтобы отображать только свойства параметров пользователей.  
  
### <a name="to-add-a-user-setting-property-grid"></a>Добавление таблицы свойств параметров пользователей  
  
1.  Добавьте элемент управления **PropertyGrid** из **панели элементов** в область конструктора для вашего приложения (здесь предполагается приложение `Form1`).  
  
     Имя по умолчанию элемента управления таблицы свойств — `PropertyGrid1`.  
  
2.  Дважды щелкните область конструктора для `Form1`, чтобы открыть код обработчика событий загрузки формы.  
  
3.  Задайте объект `My.Settings` в качестве выделенного объекта для таблицы свойств.  
  
     [!code-vb[VbVbalrMyResources#11](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_1.vb)]  
  
4.  Настройте таблицу свойств для отображения только параметров пользователей.  
  
     [!code-vb[VbVbalrMyResources#12](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_2.vb)]  
  
    > [!NOTE]
    >  Чтобы отобразить только параметры области определения приложения, используйте атрибут <xref:System.Configuration.ApplicationScopedSettingAttribute> вместо <xref:System.Configuration.UserScopedSettingAttribute>.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Приложение сохраняет пользовательские параметры при завершении работы. Чтобы сохранить параметры немедленно, вызовите метод `My.Settings.Save`. Дополнительные сведения см. в разделе [Практическое руководство. Сохранение пользовательских параметров в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).  
  
## <a name="see-also"></a>См. также  
 [Объект My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [Практическое руководство. Чтение параметров приложения в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [Практическое руководство. Изменение пользовательских параметров в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [Практическое руководство. Сохранение пользовательских параметров в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [Управление параметрами приложения (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)
