---
title: Практическое руководство. Реализация функций обратного вызова
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- callback function, implementing
ms.assetid: e55b3712-b9ea-4453-bd9a-ad5cfa2f6bfa
ms.openlocfilehash: 23355e16127b45c26a1d950c6a8b3cc27e265781
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123886"
---
# <a name="how-to-implement-callback-functions"></a>Практическое руководство. Реализация функций обратного вызова
В приведенных ниже процедуре и примере показано, как, используя вызов неуправляемого кода, можно напечатать из управляемого приложения значение дескриптора для каждого окна на локальном компьютере. В частности, для печати значения дескриптора окна в процедуре и примере используется функция **EnumWindows**, которая просматривает список окон, и управляемая функция обратного вызова CallBack.  
  
### <a name="to-implement-a-callback-function"></a>Реализация функции обратного вызова  
  
1. Прежде чем приступить к реализации, обратите внимание на сигнатуру функции **EnumWindows**. Функция **EnumWindows** имеет следующую сигнатуру:  
  
    ```cpp
    BOOL EnumWindows(WNDENUMPROC lpEnumFunc, LPARAM lParam)
    ```
  
     Признаком необходимости обратного вызова для функции является наличие аргумента **lpEnumFunc**. Обычно в именах аргументов, которые принимают указатель на функцию обратного вызова, присутствует префикс **lp** (long pointer, длинный указатель) и суффикс **Func**. Документацию по функциям Win32 см. в Microsoft Platform SDK.  
  
2. Создайте управляемую функцию обратного вызова. В примере объявляется тип делегата `CallBack`, который принимает два аргумента (**hwnd** и **lparam**). Первый аргумент — это дескриптор окна, а второй определяется приложением. В этом выпуске оба аргумента должны быть целыми числами.  
  
     Функции обратного вызова обычно возвращают ненулевые значения, сообщая об успешном выполнении, и ноль, сообщая о сбое. В этом примере для продолжения перечисления в явном виде устанавливается возвращаемое значение **true**.  
  
3. Создайте делегат и передайте его в качестве аргумента в функцию **EnumWindows**. Вызов неуправляемого кода автоматически преобразует делегат в знакомый формат обратного вызова.  
  
4. Убедитесь в том, что сборщик мусора не освобождает делегат до завершения выполнения функции обратного вызова. При передаче делегата в качестве параметра или поля структуры он не уничтожается в течение всего вызова. Таким образом, как показано в примере перечисления ниже, функция обратного вызова завершает работу, прежде чем вызов возвращает управление, не требуя никаких дополнительных действий со стороны управляемого вызывающего объекта.  
  
     Но если функция обратного вызова может быть вызвана после возвращения вызова, управляемый вызывающий объект должен выполнить действия, гарантирующие, что делегат не будет уничтожен, пока функция обратного вызова не завершит работу. Подробную информацию о предотвращении сборки мусора см. в разделе [Маршалинг взаимодействия](interop-marshaling.md) в подразделе, посвященном вызову неуправляемого кода.  
  
## <a name="example"></a>Пример  
  
```vb  
Imports System  
Imports System.Runtime.InteropServices  
  
Public Delegate Function CallBack( _  
hwnd As Integer, lParam As Integer) As Boolean  
  
Public Class EnumReportApp  
  
    Declare Function EnumWindows Lib "user32" ( _  
       x As CallBack, y As Integer) As Integer  
  
    Public Shared Sub Main()  
        EnumWindows(AddressOf EnumReportApp.Report, 0)  
    End Sub 'Main  
  
    Public Shared Function Report(hwnd As Integer, lParam As Integer) _  
    As Boolean  
        Console.Write("Window handle is ")  
        Console.WriteLine(hwnd)  
        Return True  
    End Function 'Report  
End Class 'EnumReportApp  
```  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
  
public delegate bool CallBack(int hwnd, int lParam);  
  
public class EnumReportApp  
{  
    [DllImport("user32")]  
    public static extern int EnumWindows(CallBack x, int y);   
  
    public static void Main()   
    {  
        CallBack myCallBack = new CallBack(EnumReportApp.Report);  
        EnumWindows(myCallBack, 0);  
    }  
  
    public static bool Report(int hwnd, int lParam)  
    {   
        Console.Write("Window handle is ");  
        Console.WriteLine(hwnd);  
        return true;  
    }  
}  
```  
  
```cpp  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
// A delegate type.  
delegate bool CallBack(int hwnd, int lParam);  
  
// Managed type with the method to call.  
ref class EnumReport  
{  
// Report the window handle.  
public:  
    [DllImport("user32")]  
    static int EnumWindows(CallBack^ x, int y);  
  
    static void Main()  
    {  
        EnumReport^ er = gcnew EnumReport;  
        CallBack^ myCallBack = gcnew CallBack(&EnumReport::Report);  
        EnumWindows(myCallBack, 0);  
    }  
  
    static bool Report(int hwnd, int lParam)  
    {  
       Console::Write(L"Window handle is ");  
       Console::WriteLine(hwnd);  
       return true;  
    }  
};  
  
int main()  
{  
    EnumReport::Main();  
}  
```  
  
## <a name="see-also"></a>См. также

- [Функции обратного вызова](callback-functions.md)
- [Вызов функции DLL](calling-a-dll-function.md)
