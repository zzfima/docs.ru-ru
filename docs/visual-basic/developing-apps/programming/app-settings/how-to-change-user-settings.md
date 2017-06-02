---
title: "Практическое руководство. Изменение пользовательских параметров в Visual Basic | Документы Майкрософт"
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
- user settings, changing in Visual Basic
- user settings
- My.Settings object, changing user settings
- examples [Visual Basic], changing user settings
ms.assetid: 41250181-c594-4854-9988-8183b9eb03cf
caps.latest.revision: 18
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
ms.openlocfilehash: 70928b174125507469ad44ef2093b734bbe3d09f
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-change-user-settings-in-visual-basic"></a>Практическое руководство. Изменение пользовательских параметров в Visual Basic
Пользовательские параметры можно изменять, присваивая новое значение свойству объекта параметров `My.Settings`.  
  
 Объект `My.Settings` представляет каждый параметр в виде свойства. Имя свойства совпадает с именем параметра, а тип свойства совпадает с типом параметра. **Область** параметра определяет, доступно ли свойство только для чтения. Свойство для параметра с областью **Приложение** доступно только для чтения, а свойство для параметра с областью **Пользователь** доступно для чтения или записи. Дополнительные сведения см. в разделе [Объект My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
>  Значения параметров с областью пользователя можно изменять и сохранять во время выполнения, однако параметры с областью приложения доступны только для чтения и не могут быть изменены программным способом. Вы можете изменить параметры области приложения при создании приложения с помощью **конструктора проектов** или путем изменения файла конфигурации приложения. Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="example"></a>Пример  
 В этом примере изменяется значение пользовательского параметра `Nickname`.  
  
 [!code-vb[VbVbalrMyResources#7](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-change-user-settings_1.vb)]  
  
 Для надлежащего выполнения этого примера приложение должно иметь пользовательский параметр `Nickname` типа `String`.  
  
 Приложение сохраняет пользовательские параметры при завершении работы. Чтобы сохранить параметры немедленно, вызовите метод `My.Settings.Save`. Дополнительные сведения см. в разделе [Практическое руководство. Сохранение пользовательских параметров в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).  
  
## <a name="see-also"></a>См. также  
 [Объект My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [Практическое руководство. Чтение параметров приложения в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [Практическое руководство. Сохранение пользовательских параметров в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [Управление параметрами приложения (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)
