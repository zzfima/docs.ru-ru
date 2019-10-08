---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: b17df3cb803cfbef324b74a9dee4394fce70215b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005539"
---
# <a name="-keyfile"></a>-keyfile
Указывает файл, содержащий ключ или пару ключей, чтобы задать для сборки строгое имя.  
  
## <a name="syntax"></a>Синтаксис  
  
```console 
-keyfile:file  
```  
  
## <a name="arguments"></a>Аргументы  
 `file`  
 Обязательный. Файл, содержащий ключ. Если имя файла содержит пробел, заключите его в кавычки ("").  
  
## <a name="remarks"></a>Примечания  
 Компилятор вставляет открытый ключ в манифест сборки, а затем подписывает окончательную сборку закрытым ключом. Чтобы создать файл ключа, в командной строке введите `sn -k file`. Дополнительные сведения см. в разделе [Sn. exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md).  
  
 При компиляции с `-target:module` имя файла ключа сохраняется в модуле и включается в сборку, созданную при компиляции сборки с помощью [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 Также можно передать сведения о шифровании компилятору с помощью параметра [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md). Если требуется использовать частично подписанную сборку, применяйте параметр [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md).  
  
 Этот параметр также можно указать в исходном коде любого модуля промежуточного языка Майкрософт (<xref:System.Reflection.AssemblyKeyFileAttribute>).  
  
 Если в той же компиляции указаны значения `-keyfile` и [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) (либо с помощью параметра командной строки, либо с помощью пользовательского атрибута), компилятор сначала пытается попытаться контейнер ключей. В случае успеха сборка подписывается данными контейнера ключей. Если компилятор не находит контейнер ключей, он пытается выполнить файл, заданный параметром `-keyfile`. В случае успешности сборка подписывается данными из файла ключей, а сведения о ключах устанавливаются в контейнер ключей (аналогично `sn -i`), поэтому при следующей компиляции контейнер ключей будет действительным.  
  
 Обратите внимание, что файл ключей может содержать только открытый ключ.  
  
 Дополнительные сведения о подписывании сборки см. в разделе [Создание и использование сборок со строгими именами](../../../standard/assembly/create-use-strong-named.md) .  
  
> [!NOTE]
> Параметр `-keyfile` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует исходный файл `Input.vb` и задает файл ключа.  
  
```console  
vbc -keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a>См. также

- [Сборки в .NET](../../../standard/assembly/index.md)
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
