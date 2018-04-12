---
title: '&#39; Dir &#39; функция должна первый раз вызываться с &#39; Путь к &#39; Аргумент'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 843918fe9cb0b9dece076b5dc1373c3571588caa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="39dir39-function-must-first-be-called-with-a-39pathname39-argument"></a>&#39; Dir &#39; функция должна первый раз вызываться с &#39; Путь к &#39; Аргумент
Исходный вызов `Dir` не включает функцию `PathName` аргумент. Первый вызов `Dir` должен включать `PathName`, но последующие вызовы `Dir` необязательно должны включать параметры для извлечения следующего элемента.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Укажите `PathName` аргумента в вызове функции.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
