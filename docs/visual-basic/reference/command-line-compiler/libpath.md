---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: 6285deb97b05659283071b8940fe8730890b98e8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54609867"
---
# <a name="-libpath"></a>-libpath
Указывает расположение сборок, на которую указывает ссылка.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-libpath:dirList  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`dirList`|Обязательный. Разделенный точками с запятой список каталогов искать сборку, если компилятор не найден в любой текущий рабочий каталог (каталог, из которого был вызван компилятор) или системный каталог среды CLR. Если имя каталога содержит пробел, заключите имя в кавычки (» «).|  
  
## <a name="remarks"></a>Примечания  
 `-libpath` Указывает расположение сборок, указанных по [-ссылка](../../../visual-basic/reference/command-line-compiler/reference.md) параметр.  
  
 Компилятор выполняет поиск связанных сборок, для которых не указано полное имя, в следующем порядке:  
  
1.  Текущая рабочая папка. Это папка, из которой был вызван компилятор.  
  
2.  Системный каталог среды CLR.  
  
3.  Каталоги, заданные параметром `/libpath`.  
  
4.  Каталоги, указанные переменной среды LIB.  
  
 `-libpath` Параметр аддитивные; каждое следующее указание этого параметра присоединяется к предыдущим значениям.  
  
 Используйте `-reference` для указания ссылки на сборку.  
  
|Чтобы задать параметр/LIBPATH в Visual Studio интегрированной среды разработки|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Перейдите на вкладку **Ссылки**.<br />3.  Нажмите кнопку **пути ссылки на...**  кнопки.<br />4.  В **пути для ссылок** диалогового окна введите имя каталога в **папки:** поле.<br />5.  Нажмите кнопку **добавить папку**.|  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` для создания файла .exe. Компилятор выполняет в рабочем каталоге, в корневом каталоге диска C: и в каталоге новых сборок на диске C: для ссылки на сборки.  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a>См. также
- [Сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
