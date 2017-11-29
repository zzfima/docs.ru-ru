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
# <a name="bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a>Неверное значение контрольной суммы, не шестнадцатеричные цифры или нечетное число шестнадцатеричных цифр
Значение контрольной суммы содержит недопустимые шестнадцатеричные цифры или содержит нечетное число цифр.  
  
 Когда среда ASP.NET создает исходный файл Visual Basic (с расширением VB), она вычисляет контрольную сумму и помещает ее в скрытый исходный файл под идентификатором `#externalchecksum`. Это также может сделать и пользователь, создающий файл VB, однако лучше оставить выполнение этого процесса внутренним механизмам.  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42033  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Если ASP.NET создает исходный файл Visual Basic, перезапустите сборку проекта.  
  
2.  Если предупреждение продолжает выводиться после перезапуска, переустановите ASP.NET и повторите попытку сборки.  
  
3.  Если предупреждение не пропадает или вы не используете ASP.NET, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.  
  
## <a name="see-also"></a>См. также  
 [Обзор ASP.NET](https://msdn.microsoft.com/library/4w3ex9c2.aspx)  
 [Обращайтесь к нам](/visualstudio/ide/talk-to-us)
