---
title: -keyfile (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /keyfile
helpviewer_keywords:
- /keyfile compiler option [C#]
- -keyfile compiler option [C#]
- keyfile compiler option [C#]
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
ms.openlocfilehash: 45ab88609c26dd26a1f8bb3d68d1f579af9d3f77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33214017"
---
# <a name="-keyfile-c-compiler-options"></a>-keyfile (параметры компилятора C#)
Задает имя файла, содержащего криптографический ключ.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-keyfile:file  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|----------|----------------|  
|`file`|Имя файла, содержащего ключ строгого имени.|  
  
## <a name="remarks"></a>Примечания  
 При использовании этого параметра компилятор вставляет открытый ключ из указанного файла в манифест сборки и затем подписывает окончательную сборку закрытым ключом. Чтобы создать файл ключа, введите в командной строке sn -k `file`.  
  
 При компиляции с параметром **-target:module** имя файла ключа сохраняется в модуле и включается в сборку, создаваемую при компиляции с параметром [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).  
  
 Также можно передать сведения о шифровании компилятору с помощью параметра [-keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md). Если требуется использовать частично подписанную сборку, применяйте параметр [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md).  
  
 Если для одной процедуры компиляции одновременно заданы параметры -keyfile и -keycontainer (в командной строке или с помощью пользовательских атрибутов), то сначала будет предпринята попытка использовать контейнер ключей. В случае успеха сборка подписывается данными контейнера ключей. Если компилятору не удалось обнаружить контейнер ключей, будет предпринята попытка использовать файл, заданный параметром -keyfile. В случае успеха сборка подписывается данными из файла ключей, и эти данные о ключах будут помещены в контейнер ключей (аналогично команде sn -i); таким образом, при следующей компиляции контейнер ключей будет действителен.  
  
 Обратите внимание, что файл ключей может содержать только открытый ключ.  
  
 Дополнительные сведения см. в разделах [Создание и использование сборок со строгими именами](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) и [Отложенная подпись сборки](../../../framework/app-domains/delay-sign-assembly.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **свойств** для проекта.  
  
2.  Выберите страницу свойств **Подпись**.  
  
3.  Измените свойство **Выберите файл ключа строгого имени**.  
  
 Программный доступ к этому параметру компилятора возможен с помощью свойства <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)  
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
