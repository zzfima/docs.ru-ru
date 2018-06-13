---
title: '&#39;Dir&#39; функция должна первый раз вызываться с &#39;PathName&#39; аргумент'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 3a271d7c2c2f7b98bae8f3f6fa9b67b65e3548f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585464"
---
# <a name="39dir39-function-must-first-be-called-with-a-39pathname39-argument"></a>&#39;Dir&#39; функция должна первый раз вызываться с &#39;PathName&#39; аргумент
Исходный вызов `Dir` не включает функцию `PathName` аргумент. Первый вызов `Dir` должен включать `PathName`, но последующие вызовы `Dir` необязательно должны включать параметры для извлечения следующего элемента.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Укажите `PathName` аргумента в вызове функции.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
