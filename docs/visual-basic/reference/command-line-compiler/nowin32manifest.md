---
title: "/ nowin32manifest (Visual Basic) | Документы Microsoft"
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
- /nowin32manifest compiler option [Visual Basic]
- nowin32manifest compiler option [Visual Basic]
- -nowin32manifest compiler option [Visual Basic]
ms.assetid: c0528aae-83b3-4425-99f0-19448e9843e3
caps.latest.revision: 7
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
ms.openlocfilehash: feac0ca5008925711c12bdb54ed95d4b3d79c1ef
ms.lasthandoff: 03/13/2017

---
# <a name="nowin32manifest-visual-basic"></a>/nowin32manifest (Visual Basic)
Указывает компилятору не внедрять манифест приложения в исполняемый файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/nowin32manifest  
```  
  
## <a name="remarks"></a>Примечания  
 Когда этот параметр используется, приложение будет виртуализации в Windows Vista, если не предоставить манифест приложения в файле ресурсов Win32 или на более поздних этапах построения. Дополнительные сведения о виртуализации см. в разделе [развертывание ClickOnce в Windows Vista](https://docs.microsoft.com/visualstudio/deployment/clickonce-deployment-on-windows-vista).  
  
 Дополнительные сведения о создании манифестов см. в разделе [/win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md).  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Страница "Приложение" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)
