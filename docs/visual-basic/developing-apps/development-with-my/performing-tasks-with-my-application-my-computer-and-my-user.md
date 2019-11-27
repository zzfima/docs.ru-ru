---
title: Выполнение задач с помощью My.Application, My.Computer и My.User
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: fc9fd9093a3db4785bfc94719dbae9ec1d586050
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74329580"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a>Выполнение задач с My.Application, My.Computer и My.User (Visual Basic)

Три центральных `My` объектов, предоставляющих доступ к информации и часто используемым функциональным возможностям, — `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>) и `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>). Эти объекты можно использовать для доступа к информации, связанной с текущим приложением, компьютером, на котором установлено приложение, или текущим пользователем приложения соответственно.  
  
## <a name="myapplication-mycomputer-and-myuser"></a>My. Application, My. Computer и My. User  

 В следующих примерах показано, как можно получить сведения с помощью `My`.  
  
 [!code-vb[VbVbcnMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbcnMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#2)]  
  
 Помимо извлечения информации, члены, предоставляемые через эти три объекта, также позволяют выполнять методы, связанные с этим объектом. Например, можно получить доступ к различным методам для управления файлами или обновления реестра с помощью `My.Computer`.  
  
 Файловый ввод-вывод значительно проще и быстрее с `My`, который включает разнообразные методы и свойства для управления файлами, каталогами и дисками. Объект <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> позволяет считывать из больших структурированных файлов с разделителями или полями фиксированной ширины. Этот пример открывает `TextFieldParser` `reader` и использует его для чтения из `C:\TestFolder1\test1.txt`.  
  
 [!code-vb[VbVbalrTextFieldParser#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#23)]  
  
 `My.Application` позволяет изменить язык и региональные параметры для приложения. В следующем примере показано, как можно вызвать этот метод.  
  
 [!code-vb[VbVbcnMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Зависимость My от типа проекта](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
