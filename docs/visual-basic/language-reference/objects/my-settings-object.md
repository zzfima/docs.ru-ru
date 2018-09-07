---
title: Объект My.Settings (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: 83bba35340a917b649369fc1eb7a01a2bc6a2188
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861680"
---
# <a name="mysettings-object"></a>Объект My.Settings
Предоставляет свойства и методы для доступа к параметрам приложения.  
  
## <a name="remarks"></a>Примечания  
 `My.Settings` Объект предоставляет доступ к параметрам приложения и позволяет динамически сохранять и извлекать значения свойств и другие сведения для вашего приложения. Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="properties"></a>Свойства  
 Свойства объекта `My.Settings` обеспечивают доступ к параметрам приложения. Чтобы добавить или удалить параметры, используйте **конструктор параметров**.  
  
 Каждый параметр имеет **имя**, **тип**, **область**, и **значение**, и эти параметры определяют, как свойство для доступа к каждому параметру отображается в `My.Settings` объекта:  
  
-   **Имя** определяет имя свойства.  
  
-   **Тип** определяет тип свойства.  
  
-   **Область** указывает, является ли свойство только для чтения. Если значение равно **приложения**, свойство только для чтения; если значение равно **пользователя**, свойства чтения и записи.  
  
-   **Значение** значение свойства по умолчанию.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|---|---|  
|`Reload`|Перезагружает параметры пользователя из последними сохраненными значениями.|  
|`Save`|Сохраняет текущие параметры пользователя.|  
  
 `My.Settings` Также предоставляет дополнительные свойства и методы, унаследованные от <xref:System.Configuration.ApplicationSettingsBase> класса.  
  
## <a name="tasks"></a>Задачи  
 В следующей таблице перечислены примеры задач, связанных с `My.Settings` объекта.  
  
|Кому|См.|  
|---|---|  
|Чтение параметров приложения|[Практическое руководство. Чтение параметров приложения в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|Изменение параметров пользователя|[Практическое руководство. Изменение пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|Сохранение пользовательских параметров|[Практическое руководство. Сохранение пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|Создать таблицу свойств для пользовательских параметров|[Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
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
