---
title: -sdkpath
ms.date: 07/20/2015
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
ms.openlocfilehash: 2024ccadb06fdea0c24d9d304c2fe040f8cce1d5
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814332"
---
# <a name="-sdkpath"></a>-sdkpath
Указывает расположение библиотек mscorlib.dll и Microsoft.VisualBasic.dll.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-sdkpath:path  
```  
  
## <a name="arguments"></a>Аргументы  
 `path`  
 Каталог, содержащий версии mscorlib.dll и Microsoft.VisualBasic.dll, используемые для компиляции. Этот путь не проверяется до его загрузки. Заключите имя каталога в кавычки (» «), если он содержит пробел.  
  
## <a name="remarks"></a>Примечания  
 Этот параметр указывает компилятору Visual Basic для загрузки библиотеки mscorlib.dll и Microsoft.VisualBasic.dll файлы из расположения не по умолчанию. `-sdkpath` Параметр был разработан для использования с [- netcf](../../../visual-basic/reference/command-line-compiler/netcf.md). [!INCLUDE[Compact](~/includes/compact-md.md)] Применяются различные версии поддерживаемых библиотек, чтобы избежать использования типов и языковые компоненты, не найден на устройствах.  
  
> [!NOTE]
>  `-sdkpath` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки. `-sdkpath` Был установлен при загрузке проекта Visual Basic для устройства.  
  
 Можно указать, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic с помощью `-vbruntime` параметр компилятора. Дополнительные сведения см. в разделе [- vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `Myfile.vb` с [!INCLUDE[Compact](~/includes/compact-md.md)], с помощью версии библиотеки Mscorlib.dll и Microsoft.VisualBasic.dll см. в каталог установки по умолчанию для [!INCLUDE[Compact](~/includes/compact-md.md)] на диске C:. Как правило, используется самую последнюю версию [!INCLUDE[Compact](~/includes/compact-md.md)].  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
