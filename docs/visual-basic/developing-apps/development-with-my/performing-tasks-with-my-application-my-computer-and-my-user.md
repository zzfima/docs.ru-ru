---
title: Выполнение задач с My.Application, My.Computer и My.User (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: bc2b0521598c00cdb398d936d61d65874a9cf274
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a>Выполнение задач с My.Application, My.Computer и My.User (Visual Basic)
Три центральных `My` являются объекты, которые предоставляют доступ к информации и часто используемым функциям `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), и `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>). Эти объекты можно использовать для доступа к информации, связанной с текущего приложения, установленного приложения на компьютере или текущего пользователя или приложения, соответственно.  
  
## <a name="myapplication-mycomputer-and-myuser"></a>My.Application, My.Computer и My.User  
 В следующих примерах демонстрируется, каким образом данные можно получить с помощью `My`.  
  
 [!code-vb[VbVbcnMy#1](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_1.vb)]  
  
 [!code-vb[VbVbcnMy#2](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_2.vb)]  
  
 В дополнение к сведениям, члены, доступные через эти три объекта также позволяют выполнять методы, связанные с этим объектом. Например, доступ к различные методы для управления файлами и редактирования реестра через `My.Computer`.  
  
 Файловый ввод-вывод выполняется значительно проще и быстрее при использовании `My`, которая содержит разнообразные методы и свойства для управления файлы, папки и диски. <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> Объектов позволяет считывать из больших структурированных файлов с разделителями или поля фиксированной ширины. В этом примере открывается `TextFieldParser``reader` и использует его для чтения из `C:\TestFolder1\test1.txt`.  
  
 [!code-vb[VbVbalrTextFieldParser#23](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_3.vb)]  
  
 `My.Application` позволяет изменять язык и региональные параметры для приложения. В следующем примере показано, как можно вызвать этот метод.  
  
 [!code-vb[VbVbcnMy#3](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_4.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [Зависимость My от типа проекта](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
