---
title: "/ codepage (Visual Basic) | Документы Microsoft"
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
- /codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
caps.latest.revision: 17
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
ms.openlocfilehash: 90dce6e34e52862807e2acdbf1850699316730d1
ms.lasthandoff: 03/13/2017

---
# <a name="codepage-visual-basic"></a>/codepage (Visual Basic)
Задает кодовую страницу, используемую для всех файлов исходного кода при компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/codepage:id  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`id`|Обязательный. Компилятор использует кодовую страницу, определяемую по `id` для интерпретации кодировки исходных файлов.|  
  
## <a name="remarks"></a>Примечания  
 Для компиляции исходного кода, сохраненного в определенной кодировке, можно использовать `/codepage` для указания того, какая кодовая страница должна использоваться. `/codepage` Параметр применяется ко всем файлам исходного кода при компиляции. Дополнительные сведения см. в разделе [кодировку символов, в .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).  
  
 `/codepage` Не нужен, если файлы исходного кода были сохранены с помощью текущей кодовой страницы ANSI, Юникод или UTF-8 с подписью. [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]сохраняет все файлы исходного кода с текущей кодовой страницы ANSI по умолчанию, если пользователь не указывает другую кодировку в **кодировка** диалоговое окно. [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]использует **кодировка** диалоговое окно открытия файлов исходного кода, сохраненных с другой кодовой страницей.  
  
> [!NOTE]
>  `/codepage` Параметр не доступен в [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] среде разработки; он доступен только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
