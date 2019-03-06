---
title: -imports (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: ce59cbc834d84d19ec7f8d6d3d32b545c537173c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364675"
---
# <a name="-imports-visual-basic"></a>-imports (Visual Basic)
Импорт пространства имен из указанной сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-imports:namespaceList  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`namespaceList`|Обязательный. Разделенный запятыми список пространств имен для импорта.|  
  
## <a name="remarks"></a>Примечания  
 `-imports` Параметр импортирует любое пространство имен, определенные в текущем наборе исходных файлов или из любой сборки, на которую указывает ссылка.  
  
 Члены пространства имен, указанные с помощью `-imports` доступны для всех файлов исходного кода при компиляции. Используйте [оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для использования пространства имен в файле одного исходного кода.  
  
|Чтобы задать/imports в среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Перейдите на вкладку **Ссылки**.<br />3.  Введите имя пространства имен в поле рядом с **добавить пользовательский импорт** кнопки.<br />4.  Нажмите кнопку **добавить пользовательский импорт** кнопки.|  
  
## <a name="example"></a>Пример  
 Следующий код компилируется при `/imports:system.globalization` указан. Без него, что требует успешной компиляции `Imports System.Globalization` инструкции быть включены в начале файла исходного кода, или свойство быть полным как `System.Globalization.CultureInfo.CurrentCulture.Name`.

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a>См. также
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
