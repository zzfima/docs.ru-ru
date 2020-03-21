---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: cffc3c5f0ff3dd48ca2c74bde346a967b209dc5f
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266746"
---
# <a name="-keyfile"></a>-keyfile
Указывает файл, содержащий ключ или пару ключей, чтобы задать для сборки строгое имя.  
  
## <a name="syntax"></a>Синтаксис  
  
```console
-keyfile:file  
```  
  
## <a name="arguments"></a>Аргументы  
 `file`  
 Обязательный элемент. Файл, содержащий ключ. Если имя файла содержит пробел, приложить имя в кавычки ("").  
  
## <a name="remarks"></a>Remarks  
 Компилятор вставляет открытый ключ в монтажный манифест, а затем подписывает окончательную сборку с закрытым ключом. Чтобы создать файл ключа, в командной строке введите `sn -k file`. Для получения дополнительной информации, [см. Sn.exe (Сильные имя инструмент)](../../../framework/tools/sn-exe-strong-name-tool.md)).  
  
 Если компилировать `-target:module`с помощью, имя файла ключа удерживается в модуле и включено в сборку, которая создается при компиляции сборки с [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 Также можно передать сведения о шифровании компилятору с помощью параметра [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md). Если требуется использовать частично подписанную сборку, применяйте параметр [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md).  
  
 Вы также можете указать эту<xref:System.Reflection.AssemblyKeyFileAttribute>опцию в качестве пользовательского атрибута () в исходном коде для любого промежуточного языкового модуля Майкрософт.  
  
 В случае, если оба `-keyfile` и [-ключконтейнер](../../../visual-basic/reference/command-line-compiler/keycontainer.md) указаны (либо по опции командной строки или пользовательским атрибутом) в одной и той же компиляции, компилятор сначала пробует ключевой контейнер. В случае успеха сборка подписывается данными контейнера ключей. Если компилятор не находит контейнер ключа, он `-keyfile`пробует файл, указанный с помощью. Если это удастся, сборка подписывается с информацией в файле ключа, `sn -i`и ключевая информация устанавливается в ключевой контейнер (по аналогии с), так что при следующей компиляции, ключевой контейнер будет действителен.  
  
 Обратите внимание, что файл ключей может содержать только открытый ключ.  
  
 Для получения дополнительной информации о подписании сборки смотрите [создание и использование сильных собраний.](../../../standard/assembly/create-use-strong-named.md)  
  
> [!NOTE]
> Опция `-keyfile` недоступна в среде разработки Visual Studio; он доступен только при компиляции из командной строки.

## <a name="example"></a>Пример

Следующий код компилирует исходный файл `Input.vb` и определяет файл ключа.

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a>См. также раздел

- [Сборки в .NET](../../../standard/assembly/index.md)
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-справка (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
