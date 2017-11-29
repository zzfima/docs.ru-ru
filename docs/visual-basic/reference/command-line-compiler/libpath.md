---
title: /libpath
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2be2c460fddf2e8ea4fe1239ec073f208c072d34
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="libpath"></a>/libpath
Указывает расположение сборок, на которую указывает ссылка.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/libpath:dirList  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`dirList`|Обязательный. Разделенный точками с запятой список каталогов, компилятор должен искать сборку, если она отсутствует в либо в текущем рабочем каталоге (каталог, из которого был вызван компилятор) или системный каталог среды CLR. Если имя каталога содержит пробелы, заключите имя в кавычки (» «).|  
  
## <a name="remarks"></a>Примечания  
 `/libpath` Указывает расположение ссылок на сборки с [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) параметр.  
  
 Компилятор выполняет поиск связанных сборок, для которых не указано полное имя, в следующем порядке:  
  
1.  Текущая рабочая папка. Это папка, из которой был вызван компилятор.  
  
2.  Системный каталог среды CLR.  
  
3.  Каталоги, заданные параметром `/libpath`.  
  
4.  Каталоги, указанные переменной среды LIB.  
  
 `/libpath` Параметр аддитивными, указав его более чем один раз добавляет к предыдущим значениям.  
  
 Используйте `/reference` для указания ссылки на сборку.  
  
|Чтобы задать параметр/LIBPATH в Visual Studio интегрированной среде разработки|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Перейдите на вкладку **Ссылки**.<br />3.  Нажмите кнопку **ссылке на пути к...**  кнопки.<br />4.  В **пути для ссылок** диалогового окна введите имя каталога в **папки:** поле.<br />5.  Нажмите кнопку **добавить папку**.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` для создания файла .exe. Компилятор в рабочем каталоге, в корневом каталоге диска C: и в каталоге создания сборки на диске c: ищет ссылки на сборки.  
  
```  
vbc /libpath:c:\;"c:\New Assemblies" /reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
