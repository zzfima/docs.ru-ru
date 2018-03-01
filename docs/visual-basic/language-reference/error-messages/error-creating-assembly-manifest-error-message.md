---
title: "Ошибка при создании манифеста сборки: &lt;сообщение об ошибке&gt;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5e88d28ef787eb57b71d94f4ee51c09e9751dbff
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a>Ошибка при создании манифеста сборки: &lt;сообщение об ошибке&gt;
Компилятор [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] вызывает компоновщик сборок (Al.exe, который также называется Alink) для создания сборки с манифестом. Компоновщик сообщил об ошибке на этапе предварительного выпуска процедуры создания сборки.  
  
 Такая ситуация может возникнуть при наличии проблем с указанным файлом ключа или контейнером ключей. Чтобы использовать для сборки полную подпись, необходимо предоставить допустимый файл ключа с информацией об открытом и закрытом ключах. Чтобы использовать для сборки отложенную подпись, необходимо установить флажок **Только отложенная подпись** и предоставить допустимый файл ключа с информацией о ключах. При использовании отложенной подписи для сборки наличие закрытого ключа не требуется. Дополнительные сведения см. в разделе [Практическое руководство. Подписание сборки строгим именем](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).  
  
 **Идентификатор ошибки:** BC30140  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Просмотрите сообщение об ошибке и обратитесь к разделу [Al.exe](../../../framework/tools/al-exe-assembly-linker.md). Ошибка AL1019 дополнительные пояснения и рекомендации  
  
2.  Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Подписание сборки строгим именем](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [Страница "Подписывание" в конструкторе проектов](/visualstudio/ide/reference/signing-page-project-designer)  
 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).  
 [Обращайтесь к нам](/visualstudio/ide/talk-to-us)
