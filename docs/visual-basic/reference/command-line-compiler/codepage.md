---
title: /codepage (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 609373ed0e58eec86a703f33d48d31e27b0b7e3c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
|`id`|Обязательный. Компилятор использует кодовая страница, указанная `id` для интерпретации кодировки исходных файлов.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы скомпилировать исходный код сохранен в определенной кодировке, можно использовать `/codepage` для указания того, какая кодовая страница должна использоваться. `/codepage` Параметр применяется ко всем файлам исходного кода при компиляции. Дополнительные сведения см. в разделе [кодировка символов в .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).  
  
 `/codepage` Не нужен, если файлы исходного кода были сохранены с помощью текущей кодовой страницы ANSI, Юникод или UTF-8 с подписью. [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]сохраняет все файлы исходного кода с текущей кодовой страницы ANSI по умолчанию, если пользователь не указывает другую кодировку в **кодировка** диалоговое окно. [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]использует **кодировка** диалоговым окном открытия файлов исходного кода, сохраненных с другой кодовой страницей.  
  
> [!NOTE]
>  `/codepage` Параметр не доступен в [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] среде разработки; он доступен только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
