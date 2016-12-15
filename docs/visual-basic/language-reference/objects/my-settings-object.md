---
title: "Объект My.Settings | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "My.MySettingsProperty.Settings"
  - "My.Settings"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Settings - объект"
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Объект My.Settings
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Предоставляет свойства и методы для доступа к параметрам приложения.  
  
## <a name="remarks"></a>Примечания  
  `My.Settings` Объект предоставляет доступ к параметрам приложения и позволяет динамически сохранять и извлекать значения свойств и другие сведения для приложения. Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](/visual-studio/ide/managing-application-settings-dotnet).  
  
## <a name="properties"></a>Свойства  
 Свойства `My.Settings` обеспечивают доступ к параметрам приложения. Чтобы добавить или удалить параметры, используйте **Конструктор параметров**.  
  
 Каждый параметр имеет **имя**, **тип**, **область**, и **значение**, и эти параметры определяют, как отображается свойство для доступа к каждому параметру в `My.Settings` объекта:  
  
-   **Имя** определяет имя свойства.  
  
-   **Тип** определяет тип свойства.  
  
-   **Область** Указывает, является ли свойство только для чтения. Если значение равно **приложения**, свойство доступно только для чтения; если значение равно **пользователя**, свойства чтения и записи.  
  
-   **Значение** значение свойства по умолчанию.  
  
## <a name="methods"></a>Методы  
  
|||  
|-|-|  
|Метод|Описание|  
|`Reload`|Перезагружает параметры пользователя из последних сохраненных значений.|  
|`Save`|Сохраняет текущие параметры пользователя.|  
  
  `My.Settings` Также предоставляет дополнительные свойства и методы, унаследованные от <xref:System.Configuration.ApplicationSettingsBase> класса.  
  
## <a name="tasks"></a>Задачи  
 В следующей таблице перечислены примеры задач, связанных с `My.Settings` объекта.  
  
|||  
|-|-|  
|Целевой тип|См.|  
|Чтение параметров приложения|[Практическое руководство: чтение параметров приложения в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|Изменение параметров пользователя|[Практическое руководство: изменение пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|Сохранение параметров пользователя|[Практическое руководство: сохранение пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|Создание сетки свойств для параметров пользователя|[Практическое руководство: создание сетки свойств для параметров пользователя в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a>Пример  
 В этом примере отображается значение `Nickname` параметр.  
  
 [!code-vb[VbVbalrMyResources#14](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]  
  
 Для работы этого примера приложение должно иметь `Nickname` параметр типа `String`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Configuration.ApplicationSettingsBase>   
 [Практическое руководство: чтение параметров приложения в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [Практическое руководство: изменение пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [Практическое руководство: сохранение пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [Практическое руководство: создание сетки свойств для параметров пользователя в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [Управление параметрами приложения (.NET)](/visual-studio/ide/managing-application-settings-dotnet)