---
title: /keyfile
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b7f41b659399ae5a12663d4e359c02606bb6f952
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2017
---
# <a name="keyfile"></a>/keyfile
Указывает файл, содержащий ключ или пару ключей, чтобы задать для сборки строгое имя.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/keyfile:file  
```  
  
## <a name="arguments"></a>Аргументы  
 `file`  
 Обязательный. Файл, содержащий ключ. Если имя файла содержит пробелы, заключите имя в кавычки (» «).  
  
## <a name="remarks"></a>Примечания  
 Компилятор вставляет открытый ключ в манифест сборки, а затем подписывает окончательную сборку закрытым ключом. Чтобы создать файл ключа, введите `sn -k file` из командной строки. Дополнительные сведения см. на странице [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) (Sn.exe: средство строгих имен).  
  
 Если компиляция выполняется с `/target:module`, имя файла ключа сохраняется в модуле и включается в сборку, которая создается при компиляции с параметром [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 Также можно передать сведения о шифровании компилятору с помощью параметра [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md). Если необходимо использовать частично подписанную сборку, применяйте параметр [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md).  
  
 Этот параметр можно также указать в качестве настраиваемого атрибута (<xref:System.Reflection.AssemblyKeyFileAttribute>) в исходном коде любого модуля промежуточного языка корпорации Майкрософт.  
  
 В случае оба `/keyfile` и [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) указаны (в командной строке или с помощью настраиваемого атрибута) в одной компиляции, компилятор сначала пытается контейнера ключей. В случае успеха сборка подписывается данными контейнера ключей. Если контейнер ключей не обнаружен, функция пытается найти файл, заданный параметром `/keyfile`. Если он завершается успешно, сборка подписывается данными из файла ключей и сведения о ключах устанавливается в контейнер ключей (аналогично `sn -i`) таким образом, при следующей компиляции контейнер ключей будет недопустимым.  
  
 Обратите внимание, что файл ключей может содержать только открытый ключ.  
  
 В разделе [Создание и использование сборок](../../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md) Дополнительные сведения о подписи сборки.  
  
> [!NOTE]
>  `/keyfile` Параметр не доступен в [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] среде разработки; он доступен только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует исходный файл `Input.vb` и задает файл ключа.  
  
```  
vbc /keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Сборки и глобальный кэш сборок](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
