---
title: "Ошибка автоматизации"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 790b171b8d4022bd6d8b038c4221f24805ae42f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="automation-error"></a>Ошибка автоматизации
При выполнении метода либо при получении либо установке значения свойства переменной объекта возникла ошибка. О ней сообщило приложение, создавшее этот объект.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Проверьте свойства объекта `Err`, чтобы определить причину и характер ошибки.  
  
2.  Используйте инструкцию `On Error Resume Next` непосредственно перед инструкцией доступа, а затем выполните проверку на наличие ошибок сразу после инструкции доступа.  
  
## <a name="see-also"></a>См. также  
 [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [Обращайтесь к нам](/visualstudio/ide/talk-to-us)
