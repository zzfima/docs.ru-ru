---
title: -unsafe (параметры компилятора C#)
ms.date: 04/25/2018
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.openlocfilehash: 146299fda103567b111c66400c17edf36addd843
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "65877992"
---
# <a name="-unsafe-c-compiler-options"></a>-unsafe (параметры компилятора C#)

Параметр **-unsafe** разрешает компилировать код, в котором используется ключевое слово [unsafe](../keywords/unsafe.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [Небезопасный код и указатели](../../programming-guide/unsafe-code-pointers/index.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1. Откройте страницу **Свойства** проекта.  
  
2. Щелкните страницу свойств **Сборка**.  
  
3. Установите флажок **Разрешить небезопасный код**.  
  
### <a name="to-add-this-option-in-a-csproj-file"></a>Добавление этого параметра в CSPROJ-файл

Откройте CSPROJ-файл проекта и добавьте следующие элементы:

```xml
  <PropertyGroup>
    <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  </PropertyGroup>
```

 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.  
  
## <a name="example"></a>Пример

Скомпилируйте `in.cs` для небезопасного режима:  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a>См. также раздел

- [Параметры компилятора C# ](index.md)
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
