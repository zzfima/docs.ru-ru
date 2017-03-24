---
title: "/ win32resource | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /win32resource
- win32resource
dev_langs:
- VB
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
caps.latest.revision: 13
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
ms.openlocfilehash: 37902590d5a05d7fdb2a521f3c3de2ad88c2c502
ms.lasthandoff: 03/13/2017

---
# <a name="win32resource"></a>/win32resource
Вставляет файл ресурсов Win32 в выходной файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/win32resource:filename  
```  
  
## <a name="arguments"></a>Аргументы  
 `filename`  
 Имя файла ресурсов для добавления в выходной файл. Заключите имя файла в кавычки («»), если он содержит пробел.  
  
## <a name="remarks"></a>Примечания  
 Можно создать файл ресурсов Win32 с помощью компилятора ресурсов Microsoft Windows (RC).  
  
 Ресурс Win32 может содержать версию или растровое изображение (значок) сведения для идентификации приложения в **проводнике**. Если вы не укажете `/win32resource`, компилятор создает сведения о версии на основе версии сборки. `/win32resource` И `/win32icon` являются взаимоисключающими.  
  
 В разделе [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) ссылка [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] файл ресурсов или [/Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) присоединить [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] файла ресурсов.  
  
> [!NOTE]
>  `/win32resource` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и присоединяет файл ресурсов Win32 `Rf.res`:  
  
```  
vbc /win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
