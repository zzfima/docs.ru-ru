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
ms.openlocfilehash: 25368d23c398fb3674d5c2d75d4997f917a1c3d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937358"
---
# <a name="-sdkpath"></a>-sdkpath
Указывает расположение библиотеки mscorlib. dll и Microsoft. VisualBasic. dll.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-sdkpath:path  
```  
  
## <a name="arguments"></a>Аргументы  
 `path`  
 Каталог, содержащий версии mscorlib. dll и Microsoft. VisualBasic. dll, используемые для компиляции. Этот путь не проверяется до загрузки. Заключите имя каталога в кавычки (""), если оно содержит пробел.  
  
## <a name="remarks"></a>Примечания  
 Этот параметр указывает компилятору Visual Basic загрузить файлы mscorlib. dll и Microsoft. VisualBasic. dll из расположения, отличного от используемого по умолчанию. Параметр был разработан для использования с [-netcf.](../../../visual-basic/reference/command-line-compiler/netcf.md) `-sdkpath` .NET Compact Framework использует различные версии этих библиотек поддержки, чтобы избежать использования типов и функций языка, не найденных на устройствах.  
  
> [!NOTE]
> Этот `-sdkpath` параметр недоступен в среде разработки Visual Studio; он доступен только при компиляции из командной строки. Этот `-sdkpath` параметр задается при загрузке проекта Visual Basic устройства.  
  
 Можно указать, что компилятор должен компилироваться без ссылки на библиотеку времени выполнения Visual Basic с помощью `-vbruntime` параметра компилятора. Дополнительные сведения см. в разделе [-вбрунтиме](../../../visual-basic/reference/command-line-compiler/vbruntime.md).  
  
## <a name="example"></a>Пример  
 Следующий код компилируется `Myfile.vb` с .NET Compact Framework с использованием версий mscorlib. dll и Microsoft. VisualBasic. dll, находящихся в каталоге установки по умолчанию .NET Compact Framework на диске C. Как правило, используется самая последняя версия .NET Compact Framework.  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
