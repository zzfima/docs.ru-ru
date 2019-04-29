---
title: Ошибка автоматизации
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: 8370f744b916ce4a797c808ed58c5fc9580e6278
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935295"
---
# <a name="automation-error"></a>Ошибка автоматизации
При выполнении метода либо при получении либо установке значения свойства переменной объекта возникла ошибка. О ней сообщило приложение, создавшее этот объект.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Проверьте свойства объекта `Err`, чтобы определить причину и характер ошибки.  
  
2. Используйте инструкцию `On Error Resume Next` непосредственно перед инструкцией доступа, а затем выполните проверку на наличие ошибок сразу после инструкции доступа.  
  
## <a name="see-also"></a>См. также

- [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)
- [Обращайтесь к нам](/visualstudio/ide/talk-to-us)
