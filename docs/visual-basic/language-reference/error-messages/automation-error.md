---
title: Ошибка автоматизации
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: df153167bc8c73a2d3760c8d7db30dccfa468e35
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976147"
---
# <a name="automation-error"></a><span data-ttu-id="a2bec-102">Ошибка автоматизации</span><span class="sxs-lookup"><span data-stu-id="a2bec-102">Automation error</span></span>

<span data-ttu-id="a2bec-103">При выполнении метода либо при получении либо установке значения свойства переменной объекта возникла ошибка.</span><span class="sxs-lookup"><span data-stu-id="a2bec-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="a2bec-104">О ней сообщило приложение, создавшее этот объект.</span><span class="sxs-lookup"><span data-stu-id="a2bec-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a2bec-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="a2bec-105">To correct this error</span></span>  
  
1. <span data-ttu-id="a2bec-106">Проверьте свойства объекта `Err`, чтобы определить причину и характер ошибки.</span><span class="sxs-lookup"><span data-stu-id="a2bec-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2. <span data-ttu-id="a2bec-107">Используйте инструкцию `On Error Resume Next` непосредственно перед инструкцией доступа, а затем выполните проверку на наличие ошибок сразу после инструкции доступа.</span><span class="sxs-lookup"><span data-stu-id="a2bec-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2bec-108">См. также</span><span class="sxs-lookup"><span data-stu-id="a2bec-108">See also</span></span>

- [<span data-ttu-id="a2bec-109">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="a2bec-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="a2bec-110">Обращайтесь к нам</span><span class="sxs-lookup"><span data-stu-id="a2bec-110">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
