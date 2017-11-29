---
title: /win32icon
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 65149c617220966bc3bb6897d757a71cd60167d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="win32icon"></a>/win32icon
Внедряет ICO-файл в выходной файл. ICO-файл представляет выходной файл в **проводнике**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/win32icon:filename  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`filename`|Чтобы добавить в выходной файл ICO-файл. Заключите имя файла в кавычки (» «), если он содержит пробелы.|  
  
## <a name="remarks"></a>Примечания  
 ICO-файл можно создать с помощью компилятора ресурсов Microsoft Windows (RC). Компилятор ресурсов вызывается при компиляции программы Visual C++; ICO-файл создается из RC-файла. `/win32icon` И `/win32resource` являются взаимоисключающими.  
  
 В разделе [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) ссылка [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] файла ресурсов или [/Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) для присоединения [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] файла ресурсов. В разделе [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) Импорт RES-файл.  
  
|Чтобы задать/win32icon в Интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Перейдите на вкладку **Приложение** .<br />3.  Измените значение в **значок** поле.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и присоединяет ICO-файл `Rf.ico`.  
  
```  
vbc /win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
