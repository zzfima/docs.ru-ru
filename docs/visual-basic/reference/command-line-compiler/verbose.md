---
title: "/ verbose | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
caps.latest.revision: 11
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f6d8a8b914ccffff72128bbc907482816b95b8a0
ms.lasthandoff: 03/13/2017

---
# <a name="verbose"></a>/verbose
Указывает компилятору создавать подробные сообщения об ошибках и состоянии.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/verbose[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательный. Указание `/verbose` же эффект достигается указанием `/verbose+`, который указывает компилятору выводить подробные сообщения. Значение по умолчанию для этого параметра — `/verbose-`.  
  
## <a name="remarks"></a>Примечания  
 `/verbose` Отображает сведения о общее количество ошибок, выдаваемых компилятором, сообщает, какие сборки загружаются модулем и отображает компилируемые файлы.  
  
> [!NOTE]
>  `/verbose` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` , а компилятор, чтобы отобразить подробные сведения о состоянии.  
  
```  
vbc /verbose in.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
