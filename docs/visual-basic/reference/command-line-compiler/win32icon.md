---
title: "/ win32icon | Документы Microsoft"
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
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
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
ms.openlocfilehash: 110a3861d6628dc2c3fb251aaa31762fb94f04c9
ms.lasthandoff: 03/13/2017

---
# <a name="win32icon"></a>/win32icon
Внедряет ICO-файл в выходной файл. Файл ICO представляет выходной файл в **проводнике**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/win32icon:filename  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`filename`|Добавить в выходной файл ICO-файл. Заключите имя файла в кавычки («»), если он содержит пробел.|  
  
## <a name="remarks"></a>Примечания  
 ICO-файл можно создать с помощью компилятора ресурсов Microsoft Windows (RC). Компилятор ресурсов вызывается при компиляции программы Visual C++; ICO-файл создается из RC-файла. `/win32icon` И `/win32resource` являются взаимоисключающими.  
  
 В разделе [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) ссылка [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] файл ресурсов или [/Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) присоединить [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] файла ресурсов. В разделе [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) Импорт RES-файл.  
  
|Установка/win32icon в Интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. На **проекта** меню, щелкните **свойства**. Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Перейдите на вкладку **Приложение** .<br />3.  Измените значение в **значок** поле.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и присоединяется файл ICO `Rf.ico`.  
  
```  
vbc /win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
