---
title: -keycontainer (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /keycontainer
helpviewer_keywords:
- /keycontainer compiler option [C#]
- keycontainer compiler option [C#]
- -keycontainer compiler option [C#]
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
ms.openlocfilehash: edb50dafa376abe55fbeeb312ca5bb8f34c83e7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-keycontainer-c-compiler-options"></a>-keycontainer (параметры компилятора C#)
Задает имя контейнера криптографического ключа.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-keycontainer:string  
```  
  
## <a name="arguments"></a>Аргументы  
 `string`  
 Имя контейнера ключа строгого имени.  
  
## <a name="remarks"></a>Примечания  
 При использовании параметра **-keycontainer** компилятор создает компонент, который можно сделать общим, вставляя в манифест сборки открытый ключ из указанного контейнера и подписывая окончательную сборку закрытым ключом. Чтобы создать файл ключа, введите в командной строке sn -k `file`. Параметр sn -i устанавливает пару ключей в контейнер.  
  
 При компиляции с параметром [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) имя файла ключа сохраняется в модуле и включается в сборку при компиляции этого модуля с параметром [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).  
  
 Этот параметр можно также указать в исходном коде любого модуля MSIL в качестве настраиваемого атрибута (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>).  
  
 Также можно передать сведения о шифровании компилятору с помощью параметра [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md). Если нужно добавить в манифест сборки открытый ключ, но при этом отложить подпись сборки до завершения ее тестирования, используйте параметр [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md).  
  
 Дополнительные сведения см. в разделах [Создание и использование сборок со строгими именами](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) и [Отложенная подпись сборки](../../../framework/app-domains/delay-sign-assembly.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Данный параметр компилятора недоступен в среде разработки Visual Studio.  
  
 Программный доступ к этому параметру компилятора возможен с помощью свойства <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)  
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
