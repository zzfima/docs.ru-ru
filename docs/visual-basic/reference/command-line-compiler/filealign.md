---
title: "/ filealign | Документы Microsoft"
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
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
caps.latest.revision: 14
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
ms.openlocfilehash: 18d5c3e327e2e41f4786eda6c3e981125f87389d
ms.lasthandoff: 03/13/2017

---
# <a name="filealign"></a>/filealign
Задает выравнивание размеров выходного файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/filealign:number  
```  
  
## <a name="arguments"></a>Аргументы  
 `number`  
 Обязательный. Значение, задающее выравнивание разделов в выходном файле. Допустимые значения: 512, 1024, 2048, 4096 и 8192. Эти значения задаются в байтах.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `/filealign` возможность задать выравнивание разделов в выходном файле. Разделы являются блоками непрерывной памяти в переносимых исполняемых (PE) файле, который содержит код или данные. `/filealign` Позволяет скомпилировать приложение с нестандартным выравниванием; большинство разработчиков не требуется использовать этот параметр.  
  
 Каждый раздел выравнивается по границе, кратной `/filealign` значение. Фиксированный по умолчанию отсутствует. Если `/filealign` не указан, компилятор выбирает значение по умолчанию во время компиляции.  
  
 Указав размер раздела, можно изменить размер выходного файла. Изменение размера раздела может применяться для программ, выполняющихся на небольших устройствах.  
  
> [!NOTE]
>  `/filealign` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
