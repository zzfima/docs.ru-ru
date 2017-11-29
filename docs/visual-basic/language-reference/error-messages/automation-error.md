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
# <a name="automation-error"></a><span data-ttu-id="0c299-102">Ошибка автоматизации</span><span class="sxs-lookup"><span data-stu-id="0c299-102">Automation error</span></span>
<span data-ttu-id="0c299-103">При выполнении метода либо при получении либо установке значения свойства переменной объекта возникла ошибка.</span><span class="sxs-lookup"><span data-stu-id="0c299-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="0c299-104">О ней сообщило приложение, создавшее этот объект.</span><span class="sxs-lookup"><span data-stu-id="0c299-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0c299-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="0c299-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="0c299-106">Проверьте свойства объекта `Err`, чтобы определить причину и характер ошибки.</span><span class="sxs-lookup"><span data-stu-id="0c299-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2.  <span data-ttu-id="0c299-107">Используйте инструкцию `On Error Resume Next` непосредственно перед инструкцией доступа, а затем выполните проверку на наличие ошибок сразу после инструкции доступа.</span><span class="sxs-lookup"><span data-stu-id="0c299-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c299-108">См. также</span><span class="sxs-lookup"><span data-stu-id="0c299-108">See Also</span></span>  
 [<span data-ttu-id="0c299-109">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="0c299-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="0c299-110">Обращайтесь к нам</span><span class="sxs-lookup"><span data-stu-id="0c299-110">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
