---
title: "/ nologo (Visual Basic) | Документы Microsoft"
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
- -nologo compiler option [Visual Basic]
- banners, suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
caps.latest.revision: 16
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
ms.openlocfilehash: a0e309a80082f19fb47ccbbb43c00f22c8addd3b
ms.lasthandoff: 03/13/2017

---
# <a name="nologo-visual-basic"></a>/nologo (Visual Basic)
Отключает отображение авторских прав и информационные сообщения во время компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/nologo  
```  
  
## <a name="remarks"></a>Примечания  
 При указании `/nologo`, компилятор не отображает авторских. По умолчанию `/nologo` не действует.  
  
> [!NOTE]
>  `/nologo` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` и не отображает авторских.  
  
```  
vbc /nologo t2.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
