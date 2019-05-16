---
title: Двоичная сериализация
ms.date: 01/02/2018
helpviewer_keywords:
- binary serialization
- serialization, about serialization
- deserialization
- binary serialization, about serialization
- binary serialization, .net core serialization
- serialization, cross-framework
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
author: ViktorHofer
ms.author: mairaw
ms.openlocfilehash: 4a061b3128f8d0952f800be7173203b62f89c672
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65639113"
---
# <a name="binary-serialization"></a>Двоичная сериализация

Сериализацию можно представить как процесс сохранения состояния объекта в среду хранения. Во время этого процесса открытые и закрытые поля объекта и имя класса, включая сборку с классом, преобразуются в поток байтов, который затем записывается в поток данных. После десериализации объекта создается точная копия исходного объекта.

При реализации механизма сериализации в объектно-ориентированной среде следует сделать выбор между простотой и гибкостью использования. Процесс можно в значительной степени автоматизировать при условии сохранения над ним достаточного контроля. Например, могут возникать ситуации, при которых недостаточно простой двоичной сериализации или по какой-либо причине необходимо определить сериализуемые поля в классе. В следующих разделах исследуется надежный механизм сериализации с использованием платформы .NET и отмечается ряд важных особенностей, которые позволяют настраивать процесс в соответствии с собственными потребностями.

> [!NOTE]
> Состояние объекта, закодированного в UTF-8 или UTF-7, не сохраняется, если этот объект сериализуется и десериализуется с использованием различных версий .NET Framework.

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

По своей природе двоичная сериализация позволяет изменять частные члены внутри объекта и таким образом изменять его состояние. В связи с этим рекомендуется использовать другие платформы сериализации, например JSON.NET, которые работают на поверхности открытого API.

## <a name="binary-serialization-in-net-core"></a>Двоичная сериализация в .NET Core

.NET Core поддерживает двоичную сериализацию с подмножеством типов. Список поддерживаемых типов представлен в [этом разделе](#serializable-types). Благодаря определенному набору типов гарантируется возможность сериализации между платформой .NET Framework версии 4.5.1 или более поздней и .NET Core 2.0 и более поздних версий. Другие реализации .NET (например Mono) официально не поддерживаются, но также должны работать.

### <a name="serializable-types"></a>Сериализуемые типы

- <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderInternalCompilerException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.AccessViolationException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.AggregateException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.ApplicationException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.ArgumentException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.ArgumentNullException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.ArgumentOutOfRangeException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.ArithmeticException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Array?displayProperty=nameWithType>
- <xref:System.ArraySegment%601?displayProperty=nameWithType>
- <xref:System.ArrayTypeMismatchException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Attribute?displayProperty=nameWithType>
- <xref:System.BadImageFormatException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Boolean?displayProperty=nameWithType>
- <xref:System.Byte?displayProperty=nameWithType>
- <xref:System.CannotUnloadAppDomainException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Char?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList?displayProperty=nameWithType>
- <xref:System.Collections.BitArray?displayProperty=nameWithType>
- <xref:System.Collections.Comparer?displayProperty=nameWithType>
- <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType>
- <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Collections.Generic.KeyValuePair%602?displayProperty=nameWithType>
- <xref:System.Collections.Generic.LinkedList%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType>
- <xref:System.Collections.Generic.SortedSet%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.Stack%601?displayProperty=nameWithType>
- <xref:System.Collections.Hashtable?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.Collection%601?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType>
- <xref:System.Collections.Queue?displayProperty=nameWithType>
- <xref:System.Collections.SortedList?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.HybridDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.ListDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.StringCollection?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.StringDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Stack?displayProperty=nameWithType>
- `System.Collections.Generic.NonRandomizedStringEqualityComparer` (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.ComponentModel.Design.CheckoutException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.ComponentModel.InvalidAsynchronousStateException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.ComponentModel.LicenseException?displayProperty=nameWithType> (доступный в .NET Core 2.0.4 и более поздних версий, сериализация с .NET Framework в .NET Core не поддерживается)
- <xref:System.ComponentModel.WarningException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.ComponentModel.Win32Exception?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Configuration.ConfigurationException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Configuration.Provider.ProviderException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Configuration.SettingsPropertyIsReadOnlyException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Configuration.SettingsPropertyNotFoundException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Configuration.SettingsPropertyWrongTypeException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.ContextMarshalException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DBNull?displayProperty=nameWithType> (доступно в .NET Core 2.0.2 и более поздних версий)
- <xref:System.Data.Common.DbException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.ConstraintException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.DBConcurrencyException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.DataException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.DataSet?displayProperty=nameWithType>
- <xref:System.Data.DataTable?displayProperty=nameWithType> (RemotingFormat равным SerializationFormat.Binary в этом случае его можно только обмениваться с .NET Core 2.1 и более поздних версий.)
- <xref:System.Data.DeletedRowInaccessibleException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.DuplicateNameException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.EvaluateException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.InRowChangingEventException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.InvalidConstraintException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.InvalidExpressionException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.MissingPrimaryKeyException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.NoNullAllowedException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.Odbc.OdbcException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.OperationAbortedException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.PropertyCollection?displayProperty=nameWithType>
- <xref:System.Data.ReadOnlyException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.RowNotInTableException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.SqlClient.SqlException?displayProperty=nameWithType> (доступный в .NET Core 2.0.4 и более поздних версий, сериализация с .NET Framework в .NET Core не поддерживается)
- <xref:System.Data.SqlTypes.SqlAlreadyFilledException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlNotFilledException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.SqlTypes.SqlNullValueException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlTruncateException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.SqlTypes.SqlTypeException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.StrongTypingException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.SyntaxErrorException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Data.VersionNotFoundException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DataMisalignedException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DateTime?displayProperty=nameWithType>
- <xref:System.DateTimeOffset?displayProperty=nameWithType>
- <xref:System.Decimal?displayProperty=nameWithType>
- `System.Diagnostics.Contracts.ContractException` (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Diagnostics.Tracing.EventSourceException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DirectoryServices.AccountManagement.MultipleMatchesException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DirectoryServices.AccountManagement.NoMatchingPrincipalException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DirectoryServices.AccountManagement.PasswordException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DirectoryServices.AccountManagement.PrincipalException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DirectoryServices.AccountManagement.PrincipalExistsException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DirectoryServices.AccountManagement.PrincipalOperationException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DirectoryServices.AccountManagement.PrincipalServerDownException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectExistsException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectNotFoundException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryOperationException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryServerDownException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DirectoryServices.ActiveDirectory.ForestTrustCollisionException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DirectoryServices.ActiveDirectory.SyncFromAllServersOperationException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DirectoryServices.DirectoryServicesCOMException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DirectoryServices.Protocols.BerConversionException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DirectoryServices.Protocols.DirectoryException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DirectoryServices.Protocols.DirectoryOperationException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DirectoryServices.Protocols.LdapException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DirectoryServices.Protocols.TlsOperationException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DivideByZeroException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.DllNotFoundException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Double?displayProperty=nameWithType>
- <xref:System.Drawing.Color?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- <xref:System.Drawing.PointF?displayProperty=nameWithType>
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>
- <xref:System.Drawing.RectangleF?displayProperty=nameWithType>
- <xref:System.Drawing.Size?displayProperty=nameWithType>
- <xref:System.Drawing.SizeF?displayProperty=nameWithType>
- <xref:System.DuplicateWaitObjectException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.EntryPointNotFoundException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Enum?displayProperty=nameWithType>
- <xref:System.EventArgs?displayProperty=nameWithType> (доступно в .NET Core 2.0.6 и более поздних версий)
- <xref:System.Exception?displayProperty=nameWithType>
- <xref:System.ExecutionEngineException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.FieldAccessException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.FormatException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Globalization.CompareInfo?displayProperty=nameWithType>
- <xref:System.Globalization.CultureNotFoundException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Globalization.SortVersion?displayProperty=nameWithType>
- <xref:System.Guid?displayProperty=nameWithType>
- `System.IO.Compression.ZLibException` (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.IO.DriveNotFoundException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.IO.EndOfStreamException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.IO.FileFormatException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.IO.FileLoadException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.IO.FileNotFoundException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.IO.IOException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.IO.InternalBufferOverflowException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.IO.InvalidDataException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.IO.IsolatedStorage.IsolatedStorageException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.IO.PathTooLongException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.InsufficientExecutionStackException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.InsufficientMemoryException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Int16?displayProperty=nameWithType>
- <xref:System.Int32?displayProperty=nameWithType>
- <xref:System.Int64?displayProperty=nameWithType>
- <xref:System.IntPtr?displayProperty=nameWithType>
- <xref:System.InvalidCastException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.InvalidOperationException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.InvalidProgramException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.InvalidTimeZoneException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.MemberAccessException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.MethodAccessException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.MissingFieldException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.MissingMemberException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.MissingMethodException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.MulticastNotSupportedException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Net.Cookie?displayProperty=nameWithType>
- <xref:System.Net.CookieCollection?displayProperty=nameWithType>
- <xref:System.Net.CookieContainer?displayProperty=nameWithType>
- <xref:System.Net.CookieException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Net.HttpListenerException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Net.Mail.SmtpException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Net.Mail.SmtpFailedRecipientException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Net.Mail.SmtpFailedRecipientsException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Net.NetworkInformation.NetworkInformationException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Net.NetworkInformation.PingException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Net.ProtocolViolationException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Net.Sockets.SocketException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Net.WebException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Net.WebSockets.WebSocketException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.NotFiniteNumberException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.NotImplementedException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.NotSupportedException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.NullReferenceException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Nullable%601?displayProperty=nameWithType>
- <xref:System.Numerics.BigInteger?displayProperty=nameWithType>
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- <xref:System.Object?displayProperty=nameWithType>
- <xref:System.ObjectDisposedException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.OperationCanceledException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.OutOfMemoryException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.OverflowException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.PlatformNotSupportedException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.RankException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Reflection.AmbiguousMatchException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Reflection.CustomAttributeFormatException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Reflection.InvalidFilterCriteriaException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Reflection.ReflectionTypeLoadException?displayProperty=nameWithType> (доступный в .NET Core 2.0.4 и более поздних версий, сериализация с .NET Framework в .NET Core не поддерживается)
- <xref:System.Reflection.TargetException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Reflection.TargetInvocationException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Reflection.TargetParameterCountException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Resources.MissingManifestResourceException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Resources.MissingSatelliteAssemblyException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Runtime.CompilerServices.RuntimeWrappedException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Runtime.InteropServices.COMException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Runtime.InteropServices.ExternalException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Runtime.InteropServices.InvalidComObjectException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Runtime.InteropServices.InvalidOleVariantTypeException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Runtime.InteropServices.MarshalDirectiveException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Runtime.InteropServices.SEHException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Runtime.Serialization.InvalidDataContractException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Runtime.Serialization.SerializationException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.SByte?displayProperty=nameWithType>
- <xref:System.Security.AccessControl.PrivilegeNotHeldException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Security.Authentication.AuthenticationException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Security.Authentication.InvalidCredentialException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Security.Cryptography.CryptographicException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Security.Cryptography.CryptographicUnexpectedOperationException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- `System.Security.Cryptography.Xml.CryptoSignedXmlRecursionException` (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Security.HostProtectionException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Security.Policy.PolicyException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Security.Principal.IdentityNotMappedException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Security.SecurityException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий, ограниченной сериализации данных)
- <xref:System.Security.VerificationException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Security.XmlSyntaxException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.ServiceProcess.TimeoutException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Single?displayProperty=nameWithType>
- <xref:System.StackOverflowException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.String?displayProperty=nameWithType>
- <xref:System.StringComparer?displayProperty=nameWithType>
- <xref:System.SystemException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Text.DecoderFallbackException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Text.EncoderFallbackException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Text.RegularExpressions.RegexMatchTimeoutException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Text.StringBuilder?displayProperty=nameWithType>
- <xref:System.Threading.AbandonedMutexException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Threading.BarrierPostPhaseException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Threading.LockRecursionException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Threading.SemaphoreFullException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Threading.SynchronizationLockException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Threading.Tasks.TaskSchedulerException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Threading.ThreadInterruptedException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Threading.ThreadStartException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Threading.ThreadStateException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Threading.WaitHandleCannotBeOpenedException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.TimeSpan?displayProperty=nameWithType>
- <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType>
- <xref:System.TimeZoneInfo?displayProperty=nameWithType>
- <xref:System.TimeZoneNotFoundException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.TimeoutException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Transactions.TransactionAbortedException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Transactions.TransactionException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Transactions.TransactionInDoubtException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Transactions.TransactionManagerCommunicationException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Transactions.TransactionPromotionException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Tuple?displayProperty=nameWithType>
- <xref:System.TypeAccessException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.TypeInitializationException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.TypeLoadException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.TypeUnloadedException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.UInt16?displayProperty=nameWithType>
- <xref:System.UInt32?displayProperty=nameWithType>
- <xref:System.UInt64?displayProperty=nameWithType>
- <xref:System.UIntPtr?displayProperty=nameWithType>
- <xref:System.UnauthorizedAccessException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Uri?displayProperty=nameWithType>
- <xref:System.UriFormatException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.ValueTuple?displayProperty=nameWithType> (не подлежит сериализации в .NET Framework 4.7 и более ранних версий)
- <xref:System.ValueType?displayProperty=nameWithType>
- <xref:System.Version?displayProperty=nameWithType>
- <xref:System.WeakReference%601?displayProperty=nameWithType>
- <xref:System.WeakReference?displayProperty=nameWithType>
- <xref:System.Xml.Schema.XmlSchemaException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Xml.Schema.XmlSchemaInferenceException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Xml.Schema.XmlSchemaValidationException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Xml.XPath.XPathException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Xml.XmlException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Xml.Xsl.XsltCompileException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)
- <xref:System.Xml.Xsl.XsltException?displayProperty=nameWithType> (доступно в .NET Core 2.0.4 и более поздних версий)

## <a name="in-this-section"></a>Содержание раздела

- [Концепции сериализации](../../../docs/standard/serialization/serialization-concepts.md)\
Поясняет два сценария, когда сериализация является полезной: при сохранении постоянных данных и передаче объектов между доменами приложений.

- [Базовая сериализация](../../../docs/standard/serialization/basic-serialization.md)\
Содержит описание использования двоичных модулей форматирования и модулей форматирования SOAP для сериализации объектов.

- [Выборочная сериализация](../../../docs/standard/serialization/selective-serialization.md)\
Описывает способы предотвращения сериализации некоторых членов класса.

- [Пользовательская сериализация](../../../docs/standard/serialization/custom-serialization.md)\
Содержит способы настройки сериализации для класса с использованием интерфейса <xref:System.Runtime.Serialization.ISerializable>.

- [Этапы процесса сериализации](../../../docs/standard/serialization/steps-in-the-serialization-process.md)\
Описывает образ действия при сериализации, если в модуле форматирования вызывается метод <xref:System.Runtime.Serialization.Formatter.Serialize%2A>.

- [Сериализации, независимой от версии](../../../docs/standard/serialization/version-tolerant-serialization.md)\
Объясняются способы создания сериализуемых типов, которые можно со временем изменять без выдачи приложениями исключений.

- [Правила сериализации](../../../docs/standard/serialization/serialization-guidelines.md)\
Содержит общие рекомендации по принятию решения о сериализации объекта.

## <a name="reference"></a>Ссылка

- <xref:System.Runtime.Serialization>\
Содержит классы, которые можно использовать для сериализации и десериализации объектов.

## <a name="related-sections"></a>Связанные разделы

- [Сериализация XML и SOAP](../../../docs/standard/serialization/xml-and-soap-serialization.md)\
Описывает механизм XML-сериализации , входящий в среду CLR.

- [Безопасность и сериализация](../../../docs/framework/misc/security-and-serialization.md)\
Содержит рекомендации по написанию безопасного кода, выполняющего сериализацию.

- [Удаленное взаимодействие .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))\
Описывает различные методы взаимодействия, доступные в платформе .NET Framework для удаленного взаимодействия.

- [Веб-служб XML, созданных с помощью ASP.NET и клиентов веб-служб XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))\
Содержит разделы, посвященные программированию XML-веб-служб, созданных с помощью ASP.NET.
