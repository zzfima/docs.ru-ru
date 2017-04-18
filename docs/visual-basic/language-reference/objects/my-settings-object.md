---
title: "Объект My.Settings | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
dev_langs:
- VB
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
caps.latest.revision: 16
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d48d3556f55ef286e2f501e2df5bf5035d3aff90
ms.lasthandoff: 03/13/2017

---
# <a name="mysettings-object"></a>Объект My.Settings
Предоставляет свойства и методы для доступа к параметрам приложения.  
  
## <a name="remarks"></a>Примечания  
 `My.Settings` Объект предоставляет доступ к параметрам приложения и позволяет динамически сохранять и извлекать значения свойств и другие сведения для приложения. Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="properties"></a>Свойства  
 Свойства `My.Settings` обеспечивают доступ к параметрам приложения. Чтобы добавить или удалить параметры, используйте **конструктор параметров**.  
  
 Каждый параметр имеет **имя**, **тип**, **область**, и **значение**, и эти параметры определяют, как отображается свойство для доступа к каждому параметру в `My.Settings` объекта:  
  
-   **Имя** определяет имя свойства.  
  
-   **Тип** определяет тип свойства.  
  
-   **Область** указывает, является ли свойство только для чтения. Если значение равно **приложения**, свойство доступно только для чтения; если значение **пользователя**, свойства чтения и записи.  
  
-   **Значение** значение свойства по умолчанию.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|---|---|  
|`Reload`|Перезагружает параметры пользователя из последних сохраненных значений.|  
|`Save`|Сохраняет текущие параметры пользователя.|  
  
 `My.Settings` Также предоставляет дополнительные свойства и методы, унаследованные от <xref:System.Configuration.ApplicationSettingsBase>класса.</xref:System.Configuration.ApplicationSettingsBase>  
  
## <a name="tasks"></a>Задачи  
 В следующей таблице перечислены примеры задач, связанных с `My.Settings` объекта.  
  
|Целевой тип|См.|  
|---|---|  
|Чтение параметров приложения|[Практическое руководство: чтение параметров приложения в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|Изменение параметров пользователя|[Практическое руководство: изменение пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|Сохранение параметров пользователя|[Практическое руководство: сохранение пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|Создание сетки свойств для параметров пользователя|[Практическое руководство: создание сетки свойств для параметров пользователя в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a>Пример  
 В этом примере отображается значение `Nickname` параметр.  
  
 [!code-vb[VbVbalrMyResources&#14;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]  
  
 Для работы этого примера приложение должно иметь `Nickname` параметр типа `String`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Configuration.ApplicationSettingsBase></xref:System.Configuration.ApplicationSettingsBase>   
 [Практическое руководство: чтение параметров приложения в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [Практическое руководство: изменение пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [Практическое руководство: сохранение пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [Практическое руководство: создание сетки свойств для параметров пользователя в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [Управление параметрами приложения (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)
