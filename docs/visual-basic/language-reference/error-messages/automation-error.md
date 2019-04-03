---
title: Ошибка автоматизации
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: e0ebaabb14cf5685469f88b0be3b7fece017165e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843660"
---
# <a name="automation-error"></a><span data-ttu-id="bbe08-102">Ошибка автоматизации</span><span class="sxs-lookup"><span data-stu-id="bbe08-102">Automation error</span></span>
<span data-ttu-id="bbe08-103">При выполнении метода либо при получении либо установке значения свойства переменной объекта возникла ошибка.</span><span class="sxs-lookup"><span data-stu-id="bbe08-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="bbe08-104">О ней сообщило приложение, создавшее этот объект.</span><span class="sxs-lookup"><span data-stu-id="bbe08-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bbe08-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="bbe08-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="bbe08-106">Проверьте свойства объекта `Err`, чтобы определить причину и характер ошибки.</span><span class="sxs-lookup"><span data-stu-id="bbe08-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2.  <span data-ttu-id="bbe08-107">Используйте инструкцию `On Error Resume Next` непосредственно перед инструкцией доступа, а затем выполните проверку на наличие ошибок сразу после инструкции доступа.</span><span class="sxs-lookup"><span data-stu-id="bbe08-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe08-108">См. также</span><span class="sxs-lookup"><span data-stu-id="bbe08-108">See also</span></span>

- [<span data-ttu-id="bbe08-109">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="bbe08-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="bbe08-110">Обращайтесь к нам</span><span class="sxs-lookup"><span data-stu-id="bbe08-110">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
