---
title: Практическое руководство. Создание раздела реестра и задание его значения
ms.date: 07/20/2015
f1_keywords:
- RegistryKey.CreateSubKey
- RegistryKey.SetValue
helpviewer_keywords:
- registry keys [Visual Basic], creating
- registry [Visual Basic], adding values
- registry [Visual Basic], adding keys
- registry keys [Visual Basic], setting values
- examples [Visual Basic], registry
ms.assetid: d3e40f74-c283-480c-ab18-e5e9052cd814
ms.openlocfilehash: 459c4b3f971009ee4b6b669c55bc058db0826595
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74349204"
---
# <a name="how-to-create-a-registry-key-and-set-its-value-in-visual-basic"></a>Практическое руководство. Создание раздела реестра и задание его значения в Visual Basic

Метод `CreateSubKey` объекта `My.Computer.Registry` можно использовать для создания раздела реестра.

## <a name="procedure"></a>Процедура

### <a name="to-create-a-registry-key"></a>Создание раздела реестра

- Используйте метод `CreateSubKey`, задав куст, в который нужно поместить раздел, а также имя раздела. Параметр `Subkey` нечувствителен к регистру. В этом примере создается раздел реестра `MyTestKey` в HKEY_CURRENT_USER.

    [!code-vb[VbResourceTasks#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#17)]

### <a name="to-create-a-registry-key-and-set-a-value-in-it"></a>Создание раздела реестра и задание его значения

1. Используйте метод `CreateSubkey`, задав куст, в который нужно поместить раздел, а также имя раздела. В этом примере создается раздел реестра `MyTestKey` в HKEY_CURRENT_USER.

    [!code-vb[VbResourceTasks#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#17)]

2. Задайте значение с помощью метода `SetValue`. В этом примере строке " MyTestKeyValue" присваивается значение "Это тестовое значение".

    [!code-vb[VbResourceTasks#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#14)]

## <a name="example"></a>Пример

В этом примере создается раздел реестра `MyTestKey` в HKEY_CURRENT_USER, а затем строке `MyTestKeyValue` задается значение `This is a test value`.

[!code-vb[VbResourceTasks#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#15)]

## <a name="robust-programming"></a>Отказоустойчивость

Проверьте структуру реестра и найдите подходящее место для ключа. Для этого можно, например, открыть раздел HKEY_CURRENT_USER\Software текущего пользователя и создать раздел с названием вашей компании. Затем добавьте в ключ компании значения реестра.

При чтении реестра из веб-приложения текущий пользователь зависит от проверки подлинности и олицетворения, реализованных в веб-приложении.

Безопаснее записывать данные в папку пользователя (<xref:Microsoft.Win32.Registry.CurrentUser>), чем на локальный компьютер (<xref:Microsoft.Win32.Registry.LocalMachine>).

Создавая значение реестра, необходимо решить, что делать, если это значение уже существует. Другой процесс (возможно, вредоносный) мог уже создать это значение и получить к нему доступ. Данные, добавленные в значение реестра, становятся доступными для другого процесса. Чтобы этого избежать, используйте метод <xref:Microsoft.Win32.RegistryKey.GetValue%2A>. Он возвращает `Nothing`, если данный раздел еще не существует.

Хранить секретные данные, например пароли, в реестре обычным текстом небезопасно, даже если раздел реестра защищен ACL (списком управления доступом).

При следующих условиях возможно возникновение исключения:

- Имя ключа имеет значение `Nothing` (<xref:System.ArgumentNullException>).

- У пользователя нет разрешения на создание разделов реестра (<xref:System.Security.SecurityException>).

- Имя ключа превышает ограничение в 255 символов (<xref:System.ArgumentException>).

- Раздел является закрытым (<xref:System.IO.IOException>).

- Раздел реестра доступен только для чтения (<xref:System.UnauthorizedAccessException>).

## <a name="net-framework-security"></a>Безопасность .NET Framework

Для запуска этого процесса сборке нужен уровень привилегий, предоставляемый классом <xref:System.Security.Permissions.RegistryPermission>. Если процесс выполняется в контексте с частичным доверием, он может сгенерировать исключение из-за недостатка привилегий. Аналогичным образом пользователь должен иметь правильные ACL для создания и записи параметров. Например, локальное приложение, имеющее разрешение на доступ к коду, может не иметь разрешения операционной системы. Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../../../framework/misc/code-access-security-basics.md).

## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy.CurrentUser%2A>
- <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A>
- [Чтение данных из реестра и запись в реестр](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
- [Основы управления доступом для кода](../../../../framework/misc/code-access-security-basics.md)
