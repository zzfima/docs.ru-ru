---
title: Ошибка автоматизации
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: 8a00efe988eb39be75818b5c2c401b58e5f7f2ef
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54490886"
---
# <a name="automation-error"></a>Ошибка автоматизации
При выполнении метода либо при получении либо установке значения свойства переменной объекта возникла ошибка. О ней сообщило приложение, создавшее этот объект.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Проверьте свойства объекта `Err`, чтобы определить причину и характер ошибки.  
  
2.  Используйте инструкцию `On Error Resume Next` непосредственно перед инструкцией доступа, а затем выполните проверку на наличие ошибок сразу после инструкции доступа.  
  
## <a name="see-also"></a>См. также
- [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)
- [Обращайтесь к нам](/visualstudio/ide/talk-to-us)
