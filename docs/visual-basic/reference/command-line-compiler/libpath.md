---
title: "/ LIBPATH | Документы Microsoft"
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
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: cc534e782cff34f0c4882f3da2af973fed69ff80
ms.lasthandoff: 03/13/2017

---
# <a name="libpath"></a>/libpath
Указывает расположение сборок, на которые имеются ссылки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/libpath:dirList  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`dirList`|Обязательный. Разделенный точками с запятыми список каталогов, по которому компилятор будет искать сборку, если не найден либо в текущем рабочем каталоге (каталоге, из которого был вызван компилятор) и системном каталоге среды CLR. Если имя каталога содержит пробел, заключите имя в кавычки (» «).|  
  
## <a name="remarks"></a>Примечания  
 `/libpath` Указывает расположение ссылок на сборки с [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) параметр.  
  
 Компилятор выполняет поиск ссылок на сборки, которые не указано полное имя, в следующем порядке:  
  
1.  Текущий рабочий каталог. Это каталог, из которого был вызван компилятор.  
  
2.  Системном каталоге среды выполнения.  
  
3.  Каталоги, заданные параметром `/libpath`.  
  
4.  Каталоги, указанные в переменной среды LIB.  
  
 `/libpath` Параметр аддитивны, указав его несколько раз добавляет к предыдущим значениям.  
  
 Используйте `/reference` для указания ссылки на сборку.  
  
|Чтобы установить параметр/LIBPATH в Visual Studio интегрированная среда разработки|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. На **проекта** меню, щелкните **свойства**. Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Щелкните **ссылки** вкладки.<br />3.  Щелкните **ссылающиеся на пути... ** кнопки.<br />4.  В **пути для ссылок** диалогового окна введите имя каталога в **папки:** поле.<br />5.  Щелкните **добавить папку**.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` для создания файла .exe. Компилятор в рабочем каталоге, в корневом каталоге диска C: и в каталоге создания сборки на диске c: ищет ссылки на сборки.  
  
```  
vbc /libpath:c:\;"c:\New Assemblies" /reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
