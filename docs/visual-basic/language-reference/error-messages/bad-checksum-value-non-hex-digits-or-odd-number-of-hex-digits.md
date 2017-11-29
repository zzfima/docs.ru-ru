---
title: "Неверное значение контрольной суммы, не шестнадцатеричные цифры или нечетное число шестнадцатеричных цифр"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42033
- vbc42033
helpviewer_keywords: BC42033
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1158742c8eaa51bcbb5607795f16ae6c2b570db4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a><span data-ttu-id="af67a-102">Неверное значение контрольной суммы, не шестнадцатеричные цифры или нечетное число шестнадцатеричных цифр</span><span class="sxs-lookup"><span data-stu-id="af67a-102">Bad checksum value, non hex digits or odd number of hex digits</span></span>
<span data-ttu-id="af67a-103">Значение контрольной суммы содержит недопустимые шестнадцатеричные цифры или содержит нечетное число цифр.</span><span class="sxs-lookup"><span data-stu-id="af67a-103">A checksum value contains invalid hexadecimal digits or has an odd number of digits.</span></span>  
  
 <span data-ttu-id="af67a-104">Когда среда ASP.NET создает исходный файл Visual Basic (с расширением VB), она вычисляет контрольную сумму и помещает ее в скрытый исходный файл под идентификатором `#externalchecksum`.</span><span class="sxs-lookup"><span data-stu-id="af67a-104">When ASP.NET generates a Visual Basic source file (extension .vb), it calculates a checksum and places it in a hidden source file identified by `#externalchecksum`.</span></span> <span data-ttu-id="af67a-105">Это также может сделать и пользователь, создающий файл VB, однако лучше оставить выполнение этого процесса внутренним механизмам.</span><span class="sxs-lookup"><span data-stu-id="af67a-105">It is possible for a user generating a .vb file to do this also, but this process is best left to internal use.</span></span>  
  
 <span data-ttu-id="af67a-106">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="af67a-106">By default, this message is a warning.</span></span> <span data-ttu-id="af67a-107">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="af67a-107">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="af67a-108">**Идентификатор ошибки:** BC42033</span><span class="sxs-lookup"><span data-stu-id="af67a-108">**Error ID:** BC42033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="af67a-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="af67a-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="af67a-110">Если ASP.NET создает исходный файл Visual Basic, перезапустите сборку проекта.</span><span class="sxs-lookup"><span data-stu-id="af67a-110">If ASP.NET is generating the Visual Basic source file, restart the project build.</span></span>  
  
2.  <span data-ttu-id="af67a-111">Если предупреждение продолжает выводиться после перезапуска, переустановите ASP.NET и повторите попытку сборки.</span><span class="sxs-lookup"><span data-stu-id="af67a-111">If this warning persists after restarting, reinstall ASP.NET and try the build again.</span></span>  
  
3.  <span data-ttu-id="af67a-112">Если предупреждение не пропадает или вы не используете ASP.NET, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="af67a-112">If the warning still persists, or if you are not using ASP.NET, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af67a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="af67a-113">See Also</span></span>  
 [<span data-ttu-id="af67a-114">Обзор ASP.NET</span><span class="sxs-lookup"><span data-stu-id="af67a-114">ASP.NET Overview</span></span>](https://msdn.microsoft.com/library/4w3ex9c2.aspx)  
 [<span data-ttu-id="af67a-115">Обращайтесь к нам</span><span class="sxs-lookup"><span data-stu-id="af67a-115">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
