---
title: '&#39;Dir&#39; функция сначала должен вызываться с &#39;PathName&#39; аргумент'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: f7e9ef9cc6309f24ae9f8963e910b41180c029b7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518492"
---
# <a name="39dir39-function-must-first-be-called-with-a-39pathname39-argument"></a>&#39;Dir&#39; функция сначала должен вызываться с &#39;PathName&#39; аргумент
Исходный вызов `Dir` функция не поддерживает `PathName` аргумент. Первый вызов `Dir` должен включать `PathName`, но последующие вызовы `Dir` не обязательно должны включать параметры для извлечения следующего элемента.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Укажите `PathName` аргумента в вызове функции.  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
