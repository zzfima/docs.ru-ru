---
title: Практическое руководство. Изменение пользовательских параметров
ms.date: 07/20/2015
helpviewer_keywords:
- user settings [Visual Basic], changing in Visual Basic
- user settings
- My.Settings object [Visual Basic], changing user settings
- examples [Visual Basic], changing user settings
ms.assetid: 41250181-c594-4854-9988-8183b9eb03cf
ms.openlocfilehash: d24b6d239c894788ce67b0723b4bf034050bf307
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74329617"
---
# <a name="how-to-change-user-settings-in-visual-basic"></a>Практическое руководство. Изменение пользовательских параметров в Visual Basic

Пользовательские параметры можно изменять, присваивая новое значение свойству объекта параметров `My.Settings`.  
  
 Объект `My.Settings` представляет каждый параметр в виде свойства. Имя свойства совпадает с именем параметра, а тип свойства совпадает с типом параметра. **Область** параметра определяет, доступно ли свойство только для чтения. Свойство для параметра с областью **Приложение** доступно только для чтения, а свойство для параметра с областью **Пользователь** доступно для чтения или записи. Дополнительные сведения см. в разделе [Объект My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
> Значения параметров с областью пользователя можно изменять и сохранять во время выполнения, однако параметры с областью приложения доступны только для чтения и не могут быть изменены программным способом. Вы можете изменить параметры области приложения при создании приложения с помощью **конструктора проектов** или путем изменения файла конфигурации приложения. Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="example"></a>Пример  

 В этом примере изменяется значение пользовательского параметра `Nickname`.  
  
 [!code-vb[VbVbalrMyResources#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#7)]  
  
 Для надлежащего выполнения этого примера приложение должно иметь пользовательский параметр `Nickname` типа `String`.  
  
 Приложение сохраняет пользовательские параметры при завершении работы. Чтобы сохранить параметры немедленно, вызовите метод `My.Settings.Save`. Дополнительные сведения см. в разделе [Практическое руководство. Сохранение пользовательских параметров в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).  
  
## <a name="see-also"></a>См. также

- [Объект My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md)
- [Практическое руководство. Чтение параметров приложения в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [Практическое руководство. Сохранение пользовательских параметров в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
