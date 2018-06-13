---
title: Ошибка автоматизации
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: fdd77510d03cd9e5228be1ba9ec9f746dcc0dfe4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583881"
---
# <a name="automation-error"></a><span data-ttu-id="c1d63-102">Ошибка автоматизации</span><span class="sxs-lookup"><span data-stu-id="c1d63-102">Automation error</span></span>
<span data-ttu-id="c1d63-103">При выполнении метода либо при получении либо установке значения свойства переменной объекта возникла ошибка.</span><span class="sxs-lookup"><span data-stu-id="c1d63-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="c1d63-104">О ней сообщило приложение, создавшее этот объект.</span><span class="sxs-lookup"><span data-stu-id="c1d63-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c1d63-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="c1d63-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="c1d63-106">Проверьте свойства объекта `Err`, чтобы определить причину и характер ошибки.</span><span class="sxs-lookup"><span data-stu-id="c1d63-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2.  <span data-ttu-id="c1d63-107">Используйте инструкцию `On Error Resume Next` непосредственно перед инструкцией доступа, а затем выполните проверку на наличие ошибок сразу после инструкции доступа.</span><span class="sxs-lookup"><span data-stu-id="c1d63-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1d63-108">См. также</span><span class="sxs-lookup"><span data-stu-id="c1d63-108">See Also</span></span>  
 [<span data-ttu-id="c1d63-109">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="c1d63-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="c1d63-110">Обращайтесь к нам</span><span class="sxs-lookup"><span data-stu-id="c1d63-110">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
