---
title: "Объект My.Settings"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords: My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2f744460f8ea6c6c7f5c8c5e1658bd357e910def
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="mysettings-object"></a>Объект My.Settings
Предоставляет свойства и методы для доступа к параметрам приложения.  
  
## <a name="remarks"></a>Примечания  
 `My.Settings` Объект предоставляет доступ к параметрам приложения и позволяет динамически сохранять и извлекать значения свойств и другие сведения о приложении. Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="properties"></a>Свойства  
 Свойства объекта `My.Settings` обеспечивают доступ к параметрам приложения. Чтобы добавить или удалить параметры, используйте **конструктор параметров**.  
  
 Каждый параметр имеет **имя**, **тип**, **область**, и **значение**, и эти параметры определяют, как свойство, доступ к каждому параметру отображается в `My.Settings` объекта:  
  
-   **Имя** определяет имя свойства.  
  
-   **Тип** определяет тип свойства.  
  
-   **Область** указывает, является ли свойство только для чтения. Если значение равно **приложения**, свойство доступно только для чтения; если значение равно **пользователя**, свойство доступно для чтения записи.  
  
-   **Значение** значение свойства по умолчанию.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|---|---|  
|`Reload`|Перезагружает параметры пользователя из последними сохраненными значениями.|  
|`Save`|Сохраняет текущие параметры пользователя.|  
  
 `My.Settings` Также предоставляет дополнительные свойства и методы, унаследованные от <xref:System.Configuration.ApplicationSettingsBase> класса.  
  
## <a name="tasks"></a>Задачи  
 В следующей таблице перечислены примеры задач, связанных с `My.Settings` объекта.  
  
|Целевой тип|См.|  
|---|---|  
|Чтение параметров приложения|[Практическое руководство. Чтение параметров приложения в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|Изменение параметров пользователя|[Практическое руководство. Изменение пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|Сохранение параметров пользователя|[Практическое руководство. Сохранение пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|Создание сетки свойств для параметров пользователя|[Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a>Пример  
 В этом пример выводится значение параметра `Nickname`.  
  
 [!code-vb[VbVbalrMyResources#14](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]  
  
 Для надлежащего выполнения этого примера приложение должно иметь параметр `Nickname` типа `String`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Configuration.ApplicationSettingsBase>  
 [Практическое руководство. Чтение параметров приложения в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)  
 [Практическое руководство. Изменение пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)  
 [Практическое руководство. Сохранение пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)  
 [Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
