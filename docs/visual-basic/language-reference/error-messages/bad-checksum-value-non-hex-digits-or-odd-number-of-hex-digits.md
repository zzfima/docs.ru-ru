---
title: "Неверное значение контрольной суммы, не шестнадцатеричные цифры или нечетное число шестнадцатеричных цифр | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42033
- vbc42033
dev_langs:
- VB
helpviewer_keywords:
- BC42033
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 70a8fc5e0200c15858ad1288e12b2aeb1e5303d8
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a><span data-ttu-id="0895a-102">Неверное значение контрольной суммы, не шестнадцатеричные цифры или нечетное число шестнадцатеричных цифр</span><span class="sxs-lookup"><span data-stu-id="0895a-102">Bad checksum value, non hex digits or odd number of hex digits</span></span>
<span data-ttu-id="0895a-103">Значение контрольной суммы содержит недопустимые шестнадцатеричные цифры или содержит нечетное число цифр.</span><span class="sxs-lookup"><span data-stu-id="0895a-103">A checksum value contains invalid hexadecimal digits or has an odd number of digits.</span></span>  
  
 <span data-ttu-id="0895a-104">Когда среда ASP.NET создает исходный файл Visual Basic (с расширением VB), она вычисляет контрольную сумму и помещает ее в скрытый исходный файл под идентификатором `#externalchecksum`.</span><span class="sxs-lookup"><span data-stu-id="0895a-104">When ASP.NET generates a Visual Basic source file (extension .vb), it calculates a checksum and places it in a hidden source file identified by `#externalchecksum`.</span></span> <span data-ttu-id="0895a-105">Это также может сделать и пользователь, создающий файл VB, однако лучше оставить выполнение этого процесса внутренним механизмам.</span><span class="sxs-lookup"><span data-stu-id="0895a-105">It is possible for a user generating a .vb file to do this also, but this process is best left to internal use.</span></span>  
  
 <span data-ttu-id="0895a-106">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="0895a-106">By default, this message is a warning.</span></span> <span data-ttu-id="0895a-107">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="0895a-107">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="0895a-108">**Идентификатор ошибки:** BC42033</span><span class="sxs-lookup"><span data-stu-id="0895a-108">**Error ID:** BC42033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0895a-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="0895a-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="0895a-110">Если ASP.NET создает исходный файл Visual Basic, перезапустите сборку проекта.</span><span class="sxs-lookup"><span data-stu-id="0895a-110">If ASP.NET is generating the Visual Basic source file, restart the project build.</span></span>  
  
2.  <span data-ttu-id="0895a-111">Если предупреждение продолжает выводиться после перезапуска, переустановите ASP.NET и повторите попытку сборки.</span><span class="sxs-lookup"><span data-stu-id="0895a-111">If this warning persists after restarting, reinstall ASP.NET and try the build again.</span></span>  
  
3.  <span data-ttu-id="0895a-112">Если предупреждение не пропадает или вы не используете ASP.NET, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0895a-112">If the warning still persists, or if you are not using ASP.NET, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0895a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0895a-113">See Also</span></span>  
 <span data-ttu-id="0895a-114">[Общие сведения о ASP.NET](https://msdn.microsoft.com/library/4w3ex9c2.aspx) </span><span class="sxs-lookup"><span data-stu-id="0895a-114">[ASP.NET Overview](https://msdn.microsoft.com/library/4w3ex9c2.aspx) </span></span>  
<span data-ttu-id="0895a-115"> [Обращайтесь к нам](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="0895a-115"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>
