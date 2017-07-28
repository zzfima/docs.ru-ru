---
title: "/keyfile (параметры компилятора C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /keyfile
dev_langs:
- CSharp
helpviewer_keywords:
- /keyfile compiler option [C#]
- -keyfile compiler option [C#]
- keyfile compiler option [C#]
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 4f9ccbfe7126aac3214ccf08015353eec0490cd4
ms.contentlocale: ru-ru
ms.lasthandoff: 05/10/2017

---
# <a name="keyfile-c-compiler-options"></a>/keyfile (параметры компилятора C#)
Задает имя файла, содержащего криптографический ключ.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
/keyfile:file  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|----------|----------------|  
|`file`|Имя файла, содержащего ключ строгого имени.|  
  
## <a name="remarks"></a>Примечания  
 При использовании этого параметра компилятор вставляет открытый ключ из указанного файла в манифест сборки и затем подписывает окончательную сборку закрытым ключом. Чтобы создать файл ключа, введите в командной строке sn -k `file`.  
  
 При компиляции с параметром **/target:module** имя файла ключа сохраняется в модуле и включается в сборку, создаваемую при компиляции с параметром [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).  
  
 Также можно передать сведения о шифровании компилятору с помощью параметра [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md). Если необходимо использовать частично подписанную сборку, применяйте параметр [/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md).  
  
 Если для одной процедуры компиляции одновременно заданы параметры /keyfile и /keycontainer (в командной строке или с помощью пользовательских атрибутов), то сначала будет предпринята попытка использования контейнера ключей. В случае успеха сборка подписывается данными контейнера ключей. Если компилятору не удалось обнаружить контейнер ключей, будет предпринята попытка использовать файл, заданный параметром /keyfile. В случае успеха сборка подписывается данными из файла ключей, и эти данные о ключах будут помещены в контейнер ключей (аналогично команде sn -i); таким образом, при следующей компиляции контейнер ключей будет действителен.  
  
 Обратите внимание, что файл ключей может содержать только открытый ключ.  
  
 Дополнительные сведения см. в разделах [Создание и использование сборок со строгими именами](https://msdn.microsoft.com/library/xwb8f617) и [Отложенная подпись сборки](../../../framework/app-domains/delay-sign-assembly.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **свойств** для проекта.  
  
2.  Выберите страницу свойств **Подпись**.  
  
3.  Измените свойство **Выберите файл ключа строгого имени**.  
  
 Программный доступ к этому параметру компилятора возможен с помощью свойства <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md)   
 [NIB. Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)
