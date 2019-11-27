---
title: Объект My.Settings
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: 9560a51332ea596d4cf2228f1e07c158a0457ece
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350355"
---
# <a name="mysettings-object"></a>Объект My.Settings
Предоставляет свойства и методы для доступа к параметрам приложения.  
  
## <a name="remarks"></a>Примечания  
 Объект `My.Settings` предоставляет доступ к параметрам приложения и позволяет динамически сохранять и извлекать параметры свойств и другие сведения для приложения. Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="properties"></a>Свойства  
 Свойства объекта `My.Settings` обеспечивают доступ к параметрам приложения. Чтобы добавить или удалить параметры, используйте **Конструктор параметров**.  
  
 Каждый параметр имеет **имя**, **Тип**, **область**и **значение**, и эти параметры определяют, как свойство для доступа к каждому параметру отображается в объекте `My.Settings`:  
  
- **Имя** определяет имя свойства.  
  
- **Тип** определяет тип свойства.  
  
- **Область** указывает, доступно ли свойство только для чтения. Если значение — **Application**, свойство доступно только для чтения; Если значение — **User**, свойство доступно для чтения и записи.  
  
- **Значение** является значением свойства по умолчанию.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|---|---|  
|`Reload`|Перезагружает пользовательские параметры из последних сохраненных значений.|  
|`Save`|Сохраняет текущие параметры пользователя.|  
  
 Объект `My.Settings` также предоставляет дополнительные свойства и методы, унаследованные от класса <xref:System.Configuration.ApplicationSettingsBase>.  
  
## <a name="tasks"></a>Задачи  
 В следующей таблице приведены примеры задач, в которых используется объект `My.Settings`.  
  
|Чтобы|См. раздел|  
|---|---|  
|Чтение параметра приложения|[Практическое руководство. Чтение параметров приложения в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|Изменение параметров пользователя|[Практическое руководство. Изменение пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|Сохранить параметры пользователя|[Практическое руководство. Сохранение пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|Создание сетки свойств для параметров пользователя|[Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a>Пример  
 В этом пример выводится значение параметра `Nickname`.  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 Для надлежащего выполнения этого примера приложение должно иметь параметр `Nickname` типа `String`.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Configuration.ApplicationSettingsBase>
- [Практическое руководство. Чтение параметров приложения в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [Практическое руководство. Изменение пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [Практическое руководство. Сохранение пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
