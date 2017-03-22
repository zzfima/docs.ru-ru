---
title: "/ keyfile | Документы Microsoft"
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
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: c36eac96ac6302db0b567e8249af726c807c2c6c
ms.lasthandoff: 03/13/2017

---
# <a name="keyfile"></a>/keyfile
Указывает файл, содержащий ключ или пару ключей, чтобы задать для сборки строгое имя.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/keyfile:file  
```  
  
## <a name="arguments"></a>Аргументы  
 `file`  
 Обязательный. Файл, содержащий ключ. Если имя файла содержит пробел, заключите имя в кавычки (» «).  
  
## <a name="remarks"></a>Примечания  
 Компилятор вставляет открытый ключ в манифест сборки и затем подписывает окончательную сборку закрытым ключом. Чтобы создать файл ключа, введите `sn -k file` в командной строке. Дополнительные сведения см. на странице [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) (Sn.exe: средство строгих имен).  
  
 Если компиляция выполняется с `/target:module`, имя файла ключа сохраняется в модуле и включается в сборку, созданный при компиляции с параметром [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 Сведения о шифровании можно также передать компилятору с [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md). Используйте [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) Если частично подписанной сборки.  
  
 Можно также указать этот параметр в качестве настраиваемого атрибута (<xref:System.Reflection.AssemblyKeyFileAttribute>) в исходном коде любого модуля промежуточного языка корпорации Майкрософт.</xref:System.Reflection.AssemblyKeyFileAttribute>  
  
 В случае оба `/keyfile` и [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) указаны (в командной строке или с помощью настраиваемого атрибута) в одной компиляции, компилятор сначала пытается использовать контейнер ключей. В случае успеха сборка подписывается данными контейнера ключей. Если компилятору не удается найти контейнер ключей, клиент пытается использовать файл, заданный параметром `/keyfile`. Если это завершается успешно, сборка подписывается данными из файла ключа и данные ключа устанавливается в контейнер ключей (аналогично `sn -i`) таким образом, при следующей компиляции контейнер ключей будет допустимым.  
  
 Обратите внимание, что файл ключей может содержать только открытый ключ.  
  
 В разделе [Создание и использование сборок](https://msdn.microsoft.com/library/xwb8f617) Дополнительные сведения о подписи сборки.  
  
> [!NOTE]
>  `/keyfile` Параметр не доступен в [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] среде разработки; он доступен только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует исходный файл `Input.vb` и задает файл ключа.  
  
```  
vbc /keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
