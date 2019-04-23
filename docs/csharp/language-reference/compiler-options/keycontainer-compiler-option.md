---
title: -keycontainer (параметры компилятора C#)
ms.date: 05/16/2018
f1_keywords:
- /keycontainer
helpviewer_keywords:
- /keycontainer compiler option [C#]
- keycontainer compiler option [C#]
- -keycontainer compiler option [C#]
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
ms.openlocfilehash: cf51bccc98f04c38149ec821b7064a4844d7e804
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59302781"
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
 Когда используется параметр **-keycontainer**, компилятор создает совместно используемый компонент. Компилятор вставляет открытый ключ из указанного контейнера в манифест сборки, после чего подписывает финальную сборку закрытым ключом. Чтобы создать файл ключа, в командной строке введите `sn -k file`. Команда `sn -i` устанавливает пару ключей в контейнер. Этот параметр не поддерживается, когда компилятор работает на CoreCLR. Чтобы подписать сборку при компиляции на CoreCLR, используйте параметр [-keyfile](keyfile-compiler-option.md).
  
 При компиляции с параметром [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) имя файла ключа сохраняется в модуле и включается в сборку при компиляции этого модуля с параметром [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).  
  
 Этот параметр можно также указать в исходном коде любого модуля MSIL в качестве настраиваемого атрибута (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>).  
  
 Также можно передать сведения о шифровании компилятору с помощью параметра [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md). Если нужно добавить в манифест сборки открытый ключ, но при этом отложить подпись сборки до завершения ее тестирования, используйте параметр [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md).  
  
 Дополнительные сведения см. в разделах [Создание и использование сборок со строгими именами](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) и [Отложенная подпись сборки](../../../framework/app-domains/delay-sign-assembly.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1. Данный параметр компилятора недоступен в среде разработки Visual Studio.  
  
 Программный доступ к этому параметру компилятора возможен с помощью свойства <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.  
  
## <a name="see-also"></a>См. также

- [-keyfile (параметры компилятора C#)](keyfile-compiler-option.md)
- [Параметры компилятора C# ](index.md)
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
