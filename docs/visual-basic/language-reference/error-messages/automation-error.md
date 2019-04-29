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
# <a name="automation-error"></a><span data-ttu-id="cbd35-102">Ошибка автоматизации</span><span class="sxs-lookup"><span data-stu-id="cbd35-102">Automation error</span></span>
<span data-ttu-id="cbd35-103">При выполнении метода либо при получении либо установке значения свойства переменной объекта возникла ошибка.</span><span class="sxs-lookup"><span data-stu-id="cbd35-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="cbd35-104">О ней сообщило приложение, создавшее этот объект.</span><span class="sxs-lookup"><span data-stu-id="cbd35-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cbd35-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="cbd35-105">To correct this error</span></span>  
  
1. <span data-ttu-id="cbd35-106">Проверьте свойства объекта `Err`, чтобы определить причину и характер ошибки.</span><span class="sxs-lookup"><span data-stu-id="cbd35-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2. <span data-ttu-id="cbd35-107">Используйте инструкцию `On Error Resume Next` непосредственно перед инструкцией доступа, а затем выполните проверку на наличие ошибок сразу после инструкции доступа.</span><span class="sxs-lookup"><span data-stu-id="cbd35-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbd35-108">См. также</span><span class="sxs-lookup"><span data-stu-id="cbd35-108">See also</span></span>

- [<span data-ttu-id="cbd35-109">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="cbd35-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="cbd35-110">Обращайтесь к нам</span><span class="sxs-lookup"><span data-stu-id="cbd35-110">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
