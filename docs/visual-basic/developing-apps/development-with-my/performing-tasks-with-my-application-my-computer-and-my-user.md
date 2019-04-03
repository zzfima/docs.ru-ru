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
ms.openlocfilehash: 0372fbf63f6d12e266674f92225183911aa4ca30
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834053"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a>Выполнение задач с My.Application, My.Computer и My.User (Visual Basic)
Трех центральных `My` являются объекты, которые предоставляют доступ к информации и часто используемым функциям `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), и `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>). Эти объекты можно использовать для доступа к информации, который связан с текущего приложения, к которым приложение устанавливается на или текущего пользователя приложения, соответственно.  
  
## <a name="myapplication-mycomputer-and-myuser"></a>My.Application, My.Computer и My.User  
 В следующих примерах показано, как сведения можно получить с помощью `My`.  
  
 [!code-vb[VbVbcnMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbcnMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#2)]  
  
 В дополнение к сведениям, члены, доступные через эти три объекта также позволяют выполнять методы, связанные с этим объектом. К примеру, доступны разнообразные методы для управления файлами и обновить реестр через `My.Computer`.  
  
 Файлового ввода-вывода значительно проще и быстрее с помощью `My`, который включает широкий набор методов и свойств для операции с файлами, каталогами и дисков. <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> Объекта позволяет считывать из больших структурированных файлов с разделителями или поля фиксированной ширины. В этом примере открывается `TextFieldParser` `reader` и использует его для чтения из `C:\TestFolder1\test1.txt`.  
  
 [!code-vb[VbVbalrTextFieldParser#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#23)]  
  
 `My.Application` позволяет изменить язык и региональные параметры для вашего приложения. В следующем примере показано, как можно вызвать этот метод.  
  
 [!code-vb[VbVbcnMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Зависимость My от типа проекта](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
