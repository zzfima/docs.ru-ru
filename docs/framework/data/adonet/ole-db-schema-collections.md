---
title: Коллекции схемы OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: f753f35aab0a0200da5de463a73abb9813253d11
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658459"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="37ed0-102">Коллекции схемы OLE DB</span><span class="sxs-lookup"><span data-stu-id="37ed0-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="37ed0-103">В данном разделе рассматривается поддержка коллекций схем для поставщиков OLE DB для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="37ed0-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="37ed0-104">Поставщик OLE DB для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="37ed0-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="37ed0-105">Драйвер Microsoft SQL Server OLE DB поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="37ed0-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="37ed0-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="37ed0-106">Tables</span></span>  
  
-   <span data-ttu-id="37ed0-107">Столбцы</span><span class="sxs-lookup"><span data-stu-id="37ed0-107">Columns</span></span>  
  
-   <span data-ttu-id="37ed0-108">Процедуры</span><span class="sxs-lookup"><span data-stu-id="37ed0-108">Procedures</span></span>  
  
-   <span data-ttu-id="37ed0-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="37ed0-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="37ed0-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="37ed0-110">Catalog</span></span>  
  
-   <span data-ttu-id="37ed0-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="37ed0-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="37ed0-112">Таблицы</span><span class="sxs-lookup"><span data-stu-id="37ed0-112">Tables</span></span>  
  
|<span data-ttu-id="37ed0-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="37ed0-113">ColumnName</span></span>|<span data-ttu-id="37ed0-114">DataType</span><span class="sxs-lookup"><span data-stu-id="37ed0-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37ed0-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-115">TABLE_CATALOG</span></span>|<span data-ttu-id="37ed0-116">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-116">String</span></span>|  
|<span data-ttu-id="37ed0-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="37ed0-118">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-118">String</span></span>|  
|<span data-ttu-id="37ed0-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-119">TABLE_NAME</span></span>|<span data-ttu-id="37ed0-120">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-120">String</span></span>|  
|<span data-ttu-id="37ed0-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="37ed0-121">TABLE_TYPE</span></span>|<span data-ttu-id="37ed0-122">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-122">String</span></span>|  
|<span data-ttu-id="37ed0-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="37ed0-123">TABLE_GUID</span></span>|<span data-ttu-id="37ed0-124">Guid</span><span class="sxs-lookup"><span data-stu-id="37ed0-124">Guid</span></span>|  
|<span data-ttu-id="37ed0-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37ed0-125">DESCRIPTION</span></span>|<span data-ttu-id="37ed0-126">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-126">String</span></span>|  
|<span data-ttu-id="37ed0-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="37ed0-127">TABLE_PROPID</span></span>|<span data-ttu-id="37ed0-128">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-128">Int64</span></span>|  
|<span data-ttu-id="37ed0-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37ed0-129">DATE_CREATED</span></span>|<span data-ttu-id="37ed0-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="37ed0-130">DateTime</span></span>|  
|<span data-ttu-id="37ed0-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37ed0-131">DATE_MODIFIED</span></span>|<span data-ttu-id="37ed0-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="37ed0-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="37ed0-133">Столбцы</span><span class="sxs-lookup"><span data-stu-id="37ed0-133">Columns</span></span>  
  
|<span data-ttu-id="37ed0-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="37ed0-134">ColumnName</span></span>|<span data-ttu-id="37ed0-135">DataType</span><span class="sxs-lookup"><span data-stu-id="37ed0-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37ed0-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-136">TABLE_CATALOG</span></span>|<span data-ttu-id="37ed0-137">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-137">String</span></span>|  
|<span data-ttu-id="37ed0-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="37ed0-139">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-139">String</span></span>|  
|<span data-ttu-id="37ed0-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-140">TABLE_NAME</span></span>|<span data-ttu-id="37ed0-141">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-141">String</span></span>|  
|<span data-ttu-id="37ed0-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-142">COLUMN_NAME</span></span>|<span data-ttu-id="37ed0-143">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-143">String</span></span>|  
|<span data-ttu-id="37ed0-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="37ed0-144">COLUMN_GUID</span></span>|<span data-ttu-id="37ed0-145">Guid</span><span class="sxs-lookup"><span data-stu-id="37ed0-145">Guid</span></span>|  
|<span data-ttu-id="37ed0-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="37ed0-146">COLUMN_PROPID</span></span>|<span data-ttu-id="37ed0-147">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-147">Int64</span></span>|  
|<span data-ttu-id="37ed0-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37ed0-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="37ed0-149">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-149">Int64</span></span>|  
|<span data-ttu-id="37ed0-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="37ed0-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="37ed0-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-151">Boolean</span></span>|  
|<span data-ttu-id="37ed0-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="37ed0-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="37ed0-153">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-153">String</span></span>|  
|<span data-ttu-id="37ed0-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="37ed0-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="37ed0-155">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-155">Int64</span></span>|  
|<span data-ttu-id="37ed0-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="37ed0-156">IS_NULLABLE</span></span>|<span data-ttu-id="37ed0-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-157">Boolean</span></span>|  
|<span data-ttu-id="37ed0-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="37ed0-158">DATA_TYPE</span></span>|<span data-ttu-id="37ed0-159">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-159">Int32</span></span>|  
|<span data-ttu-id="37ed0-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="37ed0-160">TYPE_GUID</span></span>|<span data-ttu-id="37ed0-161">Guid</span><span class="sxs-lookup"><span data-stu-id="37ed0-161">Guid</span></span>|  
|<span data-ttu-id="37ed0-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37ed0-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="37ed0-163">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-163">Int64</span></span>|  
|<span data-ttu-id="37ed0-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37ed0-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="37ed0-165">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-165">Int64</span></span>|  
|<span data-ttu-id="37ed0-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37ed0-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="37ed0-167">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-167">Int32</span></span>|  
|<span data-ttu-id="37ed0-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="37ed0-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="37ed0-169">Int16</span><span class="sxs-lookup"><span data-stu-id="37ed0-169">Int16</span></span>|  
|<span data-ttu-id="37ed0-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37ed0-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="37ed0-171">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-171">Int64</span></span>|  
|<span data-ttu-id="37ed0-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="37ed0-173">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-173">String</span></span>|  
|<span data-ttu-id="37ed0-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="37ed0-175">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-175">String</span></span>|  
|<span data-ttu-id="37ed0-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="37ed0-177">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-177">String</span></span>|  
|<span data-ttu-id="37ed0-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="37ed0-179">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-179">String</span></span>|  
|<span data-ttu-id="37ed0-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="37ed0-181">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-181">String</span></span>|  
|<span data-ttu-id="37ed0-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-182">COLLATION_NAME</span></span>|<span data-ttu-id="37ed0-183">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-183">String</span></span>|  
|<span data-ttu-id="37ed0-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="37ed0-185">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-185">String</span></span>|  
|<span data-ttu-id="37ed0-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="37ed0-187">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-187">String</span></span>|  
|<span data-ttu-id="37ed0-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-188">DOMAIN_NAME</span></span>|<span data-ttu-id="37ed0-189">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-189">String</span></span>|  
|<span data-ttu-id="37ed0-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37ed0-190">DESCRIPTION</span></span>|<span data-ttu-id="37ed0-191">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-191">String</span></span>|  
|<span data-ttu-id="37ed0-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="37ed0-192">COLUMN_LCID</span></span>|<span data-ttu-id="37ed0-193">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-193">Int32</span></span>|  
|<span data-ttu-id="37ed0-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="37ed0-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="37ed0-195">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-195">Int32</span></span>|  
|<span data-ttu-id="37ed0-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="37ed0-196">COLUMN_SORTID</span></span>|<span data-ttu-id="37ed0-197">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-197">Int32</span></span>|  
|<span data-ttu-id="37ed0-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="37ed0-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="37ed0-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="37ed0-199">Byte[]</span></span>|  
|<span data-ttu-id="37ed0-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="37ed0-200">IS_COMPUTED</span></span>|<span data-ttu-id="37ed0-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="37ed0-202">Процедуры</span><span class="sxs-lookup"><span data-stu-id="37ed0-202">Procedures</span></span>  
  
|<span data-ttu-id="37ed0-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="37ed0-203">ColumnName</span></span>|<span data-ttu-id="37ed0-204">DataType</span><span class="sxs-lookup"><span data-stu-id="37ed0-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37ed0-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="37ed0-206">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-206">String</span></span>|  
|<span data-ttu-id="37ed0-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="37ed0-208">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-208">String</span></span>|  
|<span data-ttu-id="37ed0-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="37ed0-210">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-210">String</span></span>|  
|<span data-ttu-id="37ed0-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="37ed0-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="37ed0-212">Int16</span><span class="sxs-lookup"><span data-stu-id="37ed0-212">Int16</span></span>|  
|<span data-ttu-id="37ed0-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="37ed0-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="37ed0-214">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-214">String</span></span>|  
|<span data-ttu-id="37ed0-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37ed0-215">DESCRIPTION</span></span>|<span data-ttu-id="37ed0-216">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-216">String</span></span>|  
|<span data-ttu-id="37ed0-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37ed0-217">DATE_CREATED</span></span>|<span data-ttu-id="37ed0-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="37ed0-218">DateTime</span></span>|  
|<span data-ttu-id="37ed0-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37ed0-219">DATE_MODIFIED</span></span>|<span data-ttu-id="37ed0-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="37ed0-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="37ed0-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="37ed0-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="37ed0-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="37ed0-222">ColumnName</span></span>|<span data-ttu-id="37ed0-223">DataType</span><span class="sxs-lookup"><span data-stu-id="37ed0-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37ed0-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="37ed0-225">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-225">String</span></span>|  
|<span data-ttu-id="37ed0-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="37ed0-227">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-227">String</span></span>|  
|<span data-ttu-id="37ed0-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="37ed0-229">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-229">String</span></span>|  
|<span data-ttu-id="37ed0-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-230">PARAMETER_NAME</span></span>|<span data-ttu-id="37ed0-231">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-231">String</span></span>|  
|<span data-ttu-id="37ed0-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37ed0-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="37ed0-233">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-233">Int32</span></span>|  
|<span data-ttu-id="37ed0-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="37ed0-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="37ed0-235">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-235">Int32</span></span>|  
|<span data-ttu-id="37ed0-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="37ed0-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="37ed0-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-237">Boolean</span></span>|  
|<span data-ttu-id="37ed0-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="37ed0-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="37ed0-239">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-239">String</span></span>|  
|<span data-ttu-id="37ed0-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="37ed0-240">IS_NULLABLE</span></span>|<span data-ttu-id="37ed0-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-241">Boolean</span></span>|  
|<span data-ttu-id="37ed0-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="37ed0-242">DATA_TYPE</span></span>|<span data-ttu-id="37ed0-243">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-243">Int32</span></span>|  
|<span data-ttu-id="37ed0-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37ed0-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="37ed0-245">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-245">Int64</span></span>|  
|<span data-ttu-id="37ed0-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37ed0-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="37ed0-247">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-247">Int64</span></span>|  
|<span data-ttu-id="37ed0-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37ed0-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="37ed0-249">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-249">Int32</span></span>|  
|<span data-ttu-id="37ed0-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="37ed0-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="37ed0-251">Int16</span><span class="sxs-lookup"><span data-stu-id="37ed0-251">Int16</span></span>|  
|<span data-ttu-id="37ed0-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37ed0-252">DESCRIPTION</span></span>|<span data-ttu-id="37ed0-253">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-253">String</span></span>|  
|<span data-ttu-id="37ed0-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-254">TYPE_NAME</span></span>|<span data-ttu-id="37ed0-255">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-255">String</span></span>|  
|<span data-ttu-id="37ed0-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="37ed0-257">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="37ed0-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="37ed0-258">Catalog</span></span>  
  
|<span data-ttu-id="37ed0-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="37ed0-259">ColumnName</span></span>|<span data-ttu-id="37ed0-260">DataType</span><span class="sxs-lookup"><span data-stu-id="37ed0-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37ed0-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-261">CATALOG_NAME</span></span>|<span data-ttu-id="37ed0-262">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-262">String</span></span>|  
|<span data-ttu-id="37ed0-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37ed0-263">DESCRIPTION</span></span>|<span data-ttu-id="37ed0-264">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="37ed0-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="37ed0-265">Indexes</span></span>  
  
|<span data-ttu-id="37ed0-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="37ed0-266">ColumnName</span></span>|<span data-ttu-id="37ed0-267">DataType</span><span class="sxs-lookup"><span data-stu-id="37ed0-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37ed0-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-268">TABLE_CATALOG</span></span>|<span data-ttu-id="37ed0-269">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-269">String</span></span>|  
|<span data-ttu-id="37ed0-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="37ed0-271">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-271">String</span></span>|  
|<span data-ttu-id="37ed0-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-272">TABLE_NAME</span></span>|<span data-ttu-id="37ed0-273">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-273">String</span></span>|  
|<span data-ttu-id="37ed0-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-274">INDEX_CATALOG</span></span>|<span data-ttu-id="37ed0-275">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-275">String</span></span>|  
|<span data-ttu-id="37ed0-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="37ed0-277">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-277">String</span></span>|  
|<span data-ttu-id="37ed0-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-278">INDEX_NAME</span></span>|<span data-ttu-id="37ed0-279">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-279">String</span></span>|  
|<span data-ttu-id="37ed0-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="37ed0-280">PRIMARY_KEY</span></span>|<span data-ttu-id="37ed0-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-281">Boolean</span></span>|  
|<span data-ttu-id="37ed0-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="37ed0-282">UNIQUE</span></span>|<span data-ttu-id="37ed0-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-283">Boolean</span></span>|  
|<span data-ttu-id="37ed0-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="37ed0-284">CLUSTERED</span></span>|<span data-ttu-id="37ed0-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-285">Boolean</span></span>|  
|<span data-ttu-id="37ed0-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="37ed0-286">TYPE</span></span>|<span data-ttu-id="37ed0-287">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-287">Int32</span></span>|  
|<span data-ttu-id="37ed0-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="37ed0-288">FILL_FACTOR</span></span>|<span data-ttu-id="37ed0-289">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-289">Int32</span></span>|  
|<span data-ttu-id="37ed0-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="37ed0-290">INITIAL_SIZE</span></span>|<span data-ttu-id="37ed0-291">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-291">Int32</span></span>|  
|<span data-ttu-id="37ed0-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="37ed0-292">NULLS</span></span>|<span data-ttu-id="37ed0-293">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-293">Int32</span></span>|  
|<span data-ttu-id="37ed0-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="37ed0-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="37ed0-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-295">Boolean</span></span>|  
|<span data-ttu-id="37ed0-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="37ed0-296">AUTO_UPDATE</span></span>|<span data-ttu-id="37ed0-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-297">Boolean</span></span>|  
|<span data-ttu-id="37ed0-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="37ed0-298">NULL_COLLATION</span></span>|<span data-ttu-id="37ed0-299">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-299">Int32</span></span>|  
|<span data-ttu-id="37ed0-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37ed0-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="37ed0-301">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-301">Int64</span></span>|  
|<span data-ttu-id="37ed0-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-302">COLUMN_NAME</span></span>|<span data-ttu-id="37ed0-303">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-303">String</span></span>|  
|<span data-ttu-id="37ed0-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="37ed0-304">COLUMN_GUID</span></span>|<span data-ttu-id="37ed0-305">Guid</span><span class="sxs-lookup"><span data-stu-id="37ed0-305">Guid</span></span>|  
|<span data-ttu-id="37ed0-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="37ed0-306">COLUMN_PROPID</span></span>|<span data-ttu-id="37ed0-307">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-307">Int64</span></span>|  
|<span data-ttu-id="37ed0-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="37ed0-308">COLLATION</span></span>|<span data-ttu-id="37ed0-309">Int16</span><span class="sxs-lookup"><span data-stu-id="37ed0-309">Int16</span></span>|  
|<span data-ttu-id="37ed0-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="37ed0-310">CARDINALITY</span></span>|<span data-ttu-id="37ed0-311">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="37ed0-311">Decimal</span></span>|  
|<span data-ttu-id="37ed0-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="37ed0-312">PAGES</span></span>|<span data-ttu-id="37ed0-313">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-313">Int32</span></span>|  
|<span data-ttu-id="37ed0-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="37ed0-314">FILTER_CONDITION</span></span>|<span data-ttu-id="37ed0-315">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-315">String</span></span>|  
|<span data-ttu-id="37ed0-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="37ed0-316">INTEGRATED</span></span>|<span data-ttu-id="37ed0-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="37ed0-318">Поставщик Microsoft OLE DB для Oracle</span><span class="sxs-lookup"><span data-stu-id="37ed0-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="37ed0-319">Драйвер OLE DB для Oracle (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="37ed0-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="37ed0-320">Таблицы</span><span class="sxs-lookup"><span data-stu-id="37ed0-320">Tables</span></span>  
  
-   <span data-ttu-id="37ed0-321">Столбцы</span><span class="sxs-lookup"><span data-stu-id="37ed0-321">Columns</span></span>  
  
-   <span data-ttu-id="37ed0-322">Процедуры</span><span class="sxs-lookup"><span data-stu-id="37ed0-322">Procedures</span></span>  
  
-   <span data-ttu-id="37ed0-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="37ed0-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="37ed0-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="37ed0-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="37ed0-325">Представления</span><span class="sxs-lookup"><span data-stu-id="37ed0-325">Views</span></span>  
  
-   <span data-ttu-id="37ed0-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="37ed0-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="37ed0-327">Таблицы</span><span class="sxs-lookup"><span data-stu-id="37ed0-327">Tables</span></span>  
  
|<span data-ttu-id="37ed0-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="37ed0-328">ColumnName</span></span>|<span data-ttu-id="37ed0-329">DataType</span><span class="sxs-lookup"><span data-stu-id="37ed0-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37ed0-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-330">TABLE_CATALOG</span></span>|<span data-ttu-id="37ed0-331">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-331">String</span></span>|  
|<span data-ttu-id="37ed0-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="37ed0-333">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-333">String</span></span>|  
|<span data-ttu-id="37ed0-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-334">TABLE_NAME</span></span>|<span data-ttu-id="37ed0-335">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-335">String</span></span>|  
|<span data-ttu-id="37ed0-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="37ed0-336">TABLE_TYPE</span></span>|<span data-ttu-id="37ed0-337">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-337">String</span></span>|  
|<span data-ttu-id="37ed0-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="37ed0-338">TABLE_GUID</span></span>|<span data-ttu-id="37ed0-339">Guid</span><span class="sxs-lookup"><span data-stu-id="37ed0-339">Guid</span></span>|  
|<span data-ttu-id="37ed0-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37ed0-340">DESCRIPTION</span></span>|<span data-ttu-id="37ed0-341">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-341">String</span></span>|  
|<span data-ttu-id="37ed0-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="37ed0-342">TABLE_PROPID</span></span>|<span data-ttu-id="37ed0-343">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-343">Int64</span></span>|  
|<span data-ttu-id="37ed0-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37ed0-344">DATE_CREATED</span></span>|<span data-ttu-id="37ed0-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="37ed0-345">DateTime</span></span>|  
|<span data-ttu-id="37ed0-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37ed0-346">DATE_MODIFIED</span></span>|<span data-ttu-id="37ed0-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="37ed0-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="37ed0-348">Столбцы</span><span class="sxs-lookup"><span data-stu-id="37ed0-348">Columns</span></span>  
  
|<span data-ttu-id="37ed0-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="37ed0-349">ColumnName</span></span>|<span data-ttu-id="37ed0-350">DataType</span><span class="sxs-lookup"><span data-stu-id="37ed0-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37ed0-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-351">TABLE_CATALOG</span></span>|<span data-ttu-id="37ed0-352">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-352">String</span></span>|  
|<span data-ttu-id="37ed0-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="37ed0-354">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-354">String</span></span>|  
|<span data-ttu-id="37ed0-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-355">TABLE_NAME</span></span>|<span data-ttu-id="37ed0-356">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-356">String</span></span>|  
|<span data-ttu-id="37ed0-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-357">COLUMN_NAME</span></span>|<span data-ttu-id="37ed0-358">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-358">String</span></span>|  
|<span data-ttu-id="37ed0-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="37ed0-359">COLUMN_GUID</span></span>|<span data-ttu-id="37ed0-360">Guid</span><span class="sxs-lookup"><span data-stu-id="37ed0-360">Guid</span></span>|  
|<span data-ttu-id="37ed0-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="37ed0-361">COLUMN_PROPID</span></span>|<span data-ttu-id="37ed0-362">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-362">Int64</span></span>|  
|<span data-ttu-id="37ed0-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37ed0-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="37ed0-364">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-364">Int64</span></span>|  
|<span data-ttu-id="37ed0-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="37ed0-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="37ed0-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-366">Boolean</span></span>|  
|<span data-ttu-id="37ed0-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="37ed0-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="37ed0-368">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-368">String</span></span>|  
|<span data-ttu-id="37ed0-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="37ed0-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="37ed0-370">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-370">Int64</span></span>|  
|<span data-ttu-id="37ed0-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="37ed0-371">IS_NULLABLE</span></span>|<span data-ttu-id="37ed0-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-372">Boolean</span></span>|  
|<span data-ttu-id="37ed0-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="37ed0-373">DATA_TYPE</span></span>|<span data-ttu-id="37ed0-374">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-374">Int32</span></span>|  
|<span data-ttu-id="37ed0-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="37ed0-375">TYPE_GUID</span></span>|<span data-ttu-id="37ed0-376">Guid</span><span class="sxs-lookup"><span data-stu-id="37ed0-376">Guid</span></span>|  
|<span data-ttu-id="37ed0-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37ed0-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="37ed0-378">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-378">Int64</span></span>|  
|<span data-ttu-id="37ed0-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37ed0-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="37ed0-380">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-380">Int64</span></span>|  
|<span data-ttu-id="37ed0-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37ed0-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="37ed0-382">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-382">Int32</span></span>|  
|<span data-ttu-id="37ed0-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="37ed0-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="37ed0-384">Int16</span><span class="sxs-lookup"><span data-stu-id="37ed0-384">Int16</span></span>|  
|<span data-ttu-id="37ed0-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37ed0-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="37ed0-386">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-386">Int64</span></span>|  
|<span data-ttu-id="37ed0-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="37ed0-388">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-388">String</span></span>|  
|<span data-ttu-id="37ed0-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="37ed0-390">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-390">String</span></span>|  
|<span data-ttu-id="37ed0-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="37ed0-392">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-392">String</span></span>|  
|<span data-ttu-id="37ed0-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="37ed0-394">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-394">String</span></span>|  
|<span data-ttu-id="37ed0-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="37ed0-396">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-396">String</span></span>|  
|<span data-ttu-id="37ed0-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-397">COLLATION_NAME</span></span>|<span data-ttu-id="37ed0-398">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-398">String</span></span>|  
|<span data-ttu-id="37ed0-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="37ed0-400">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-400">String</span></span>|  
|<span data-ttu-id="37ed0-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="37ed0-402">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-402">String</span></span>|  
|<span data-ttu-id="37ed0-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-403">DOMAIN_NAME</span></span>|<span data-ttu-id="37ed0-404">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-404">String</span></span>|  
|<span data-ttu-id="37ed0-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37ed0-405">DESCRIPTION</span></span>|<span data-ttu-id="37ed0-406">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="37ed0-407">Процедуры</span><span class="sxs-lookup"><span data-stu-id="37ed0-407">Procedures</span></span>  
  
|<span data-ttu-id="37ed0-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="37ed0-408">ColumnName</span></span>|<span data-ttu-id="37ed0-409">DataType</span><span class="sxs-lookup"><span data-stu-id="37ed0-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37ed0-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="37ed0-411">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-411">String</span></span>|  
|<span data-ttu-id="37ed0-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="37ed0-413">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-413">String</span></span>|  
|<span data-ttu-id="37ed0-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="37ed0-415">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-415">String</span></span>|  
|<span data-ttu-id="37ed0-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="37ed0-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="37ed0-417">Int16</span><span class="sxs-lookup"><span data-stu-id="37ed0-417">Int16</span></span>|  
|<span data-ttu-id="37ed0-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="37ed0-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="37ed0-419">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-419">String</span></span>|  
|<span data-ttu-id="37ed0-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37ed0-420">DESCRIPTION</span></span>|<span data-ttu-id="37ed0-421">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-421">String</span></span>|  
|<span data-ttu-id="37ed0-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37ed0-422">DATE_CREATED</span></span>|<span data-ttu-id="37ed0-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="37ed0-423">DateTime</span></span>|  
|<span data-ttu-id="37ed0-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37ed0-424">DATE_MODIFIED</span></span>|<span data-ttu-id="37ed0-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="37ed0-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="37ed0-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="37ed0-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="37ed0-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="37ed0-427">ColumnName</span></span>|<span data-ttu-id="37ed0-428">DataType</span><span class="sxs-lookup"><span data-stu-id="37ed0-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37ed0-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="37ed0-430">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-430">String</span></span>|  
|<span data-ttu-id="37ed0-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="37ed0-432">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-432">String</span></span>|  
|<span data-ttu-id="37ed0-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="37ed0-434">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-434">String</span></span>|  
|<span data-ttu-id="37ed0-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-435">COLUMN_NAME</span></span>|<span data-ttu-id="37ed0-436">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-436">String</span></span>|  
|<span data-ttu-id="37ed0-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="37ed0-437">COLUMN_GUID</span></span>|<span data-ttu-id="37ed0-438">Guid</span><span class="sxs-lookup"><span data-stu-id="37ed0-438">Guid</span></span>|  
|<span data-ttu-id="37ed0-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="37ed0-439">COLUMN_PROPID</span></span>|<span data-ttu-id="37ed0-440">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-440">Int64</span></span>|  
|<span data-ttu-id="37ed0-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="37ed0-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="37ed0-442">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-442">Int64</span></span>|  
|<span data-ttu-id="37ed0-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37ed0-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="37ed0-444">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-444">Int64</span></span>|  
|<span data-ttu-id="37ed0-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="37ed0-445">IS_NULLABLE</span></span>|<span data-ttu-id="37ed0-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-446">Boolean</span></span>|  
|<span data-ttu-id="37ed0-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="37ed0-447">DATA_TYPE</span></span>|<span data-ttu-id="37ed0-448">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-448">Int32</span></span>|  
|<span data-ttu-id="37ed0-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="37ed0-449">TYPE_GUID</span></span>|<span data-ttu-id="37ed0-450">Guid</span><span class="sxs-lookup"><span data-stu-id="37ed0-450">Guid</span></span>|  
|<span data-ttu-id="37ed0-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37ed0-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="37ed0-452">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-452">Int64</span></span>|  
|<span data-ttu-id="37ed0-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37ed0-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="37ed0-454">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-454">Int64</span></span>|  
|<span data-ttu-id="37ed0-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37ed0-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="37ed0-456">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-456">Int32</span></span>|  
|<span data-ttu-id="37ed0-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="37ed0-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="37ed0-458">Int16</span><span class="sxs-lookup"><span data-stu-id="37ed0-458">Int16</span></span>|  
|<span data-ttu-id="37ed0-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37ed0-459">DESCRIPTION</span></span>|<span data-ttu-id="37ed0-460">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-460">String</span></span>|  
|<span data-ttu-id="37ed0-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="37ed0-461">OVERLOAD</span></span>|<span data-ttu-id="37ed0-462">Int16</span><span class="sxs-lookup"><span data-stu-id="37ed0-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="37ed0-463">Представления</span><span class="sxs-lookup"><span data-stu-id="37ed0-463">Views</span></span>  
  
|<span data-ttu-id="37ed0-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="37ed0-464">ColumnName</span></span>|<span data-ttu-id="37ed0-465">DataType</span><span class="sxs-lookup"><span data-stu-id="37ed0-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37ed0-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-466">TABLE_CATALOG</span></span>|<span data-ttu-id="37ed0-467">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-467">String</span></span>|  
|<span data-ttu-id="37ed0-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="37ed0-469">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-469">String</span></span>|  
|<span data-ttu-id="37ed0-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-470">TABLE_NAME</span></span>|<span data-ttu-id="37ed0-471">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-471">String</span></span>|  
|<span data-ttu-id="37ed0-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="37ed0-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="37ed0-473">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-473">String</span></span>|  
|<span data-ttu-id="37ed0-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="37ed0-474">CHECK_OPTION</span></span>|<span data-ttu-id="37ed0-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-475">Boolean</span></span>|  
|<span data-ttu-id="37ed0-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="37ed0-476">IS_UPDATABLE</span></span>|<span data-ttu-id="37ed0-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-477">Boolean</span></span>|  
|<span data-ttu-id="37ed0-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37ed0-478">DESCRIPTION</span></span>|<span data-ttu-id="37ed0-479">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-479">String</span></span>|  
|<span data-ttu-id="37ed0-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37ed0-480">DATE_CREATED</span></span>|<span data-ttu-id="37ed0-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="37ed0-481">DateTime</span></span>|  
|<span data-ttu-id="37ed0-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37ed0-482">DATE_MODIFIED</span></span>|<span data-ttu-id="37ed0-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="37ed0-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="37ed0-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="37ed0-484">Indexes</span></span>  
  
|<span data-ttu-id="37ed0-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="37ed0-485">ColumnName</span></span>|<span data-ttu-id="37ed0-486">DataType</span><span class="sxs-lookup"><span data-stu-id="37ed0-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37ed0-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-487">TABLE_CATALOG</span></span>|<span data-ttu-id="37ed0-488">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-488">String</span></span>|  
|<span data-ttu-id="37ed0-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="37ed0-490">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-490">String</span></span>|  
|<span data-ttu-id="37ed0-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-491">TABLE_NAME</span></span>|<span data-ttu-id="37ed0-492">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-492">String</span></span>|  
|<span data-ttu-id="37ed0-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-493">INDEX_CATALOG</span></span>|<span data-ttu-id="37ed0-494">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-494">String</span></span>|  
|<span data-ttu-id="37ed0-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="37ed0-496">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-496">String</span></span>|  
|<span data-ttu-id="37ed0-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-497">INDEX_NAME</span></span>|<span data-ttu-id="37ed0-498">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-498">String</span></span>|  
|<span data-ttu-id="37ed0-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="37ed0-499">PRIMARY_KEY</span></span>|<span data-ttu-id="37ed0-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-500">Boolean</span></span>|  
|<span data-ttu-id="37ed0-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="37ed0-501">UNIQUE</span></span>|<span data-ttu-id="37ed0-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-502">Boolean</span></span>|  
|<span data-ttu-id="37ed0-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="37ed0-503">CLUSTERED</span></span>|<span data-ttu-id="37ed0-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-504">Boolean</span></span>|  
|<span data-ttu-id="37ed0-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="37ed0-505">TYPE</span></span>|<span data-ttu-id="37ed0-506">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-506">Int32</span></span>|  
|<span data-ttu-id="37ed0-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="37ed0-507">FILL_FACTOR</span></span>|<span data-ttu-id="37ed0-508">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-508">Int32</span></span>|  
|<span data-ttu-id="37ed0-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="37ed0-509">INITIAL_SIZE</span></span>|<span data-ttu-id="37ed0-510">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-510">Int32</span></span>|  
|<span data-ttu-id="37ed0-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="37ed0-511">NULLS</span></span>|<span data-ttu-id="37ed0-512">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-512">Int32</span></span>|  
|<span data-ttu-id="37ed0-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="37ed0-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="37ed0-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-514">Boolean</span></span>|  
|<span data-ttu-id="37ed0-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="37ed0-515">AUTO_UPDATE</span></span>|<span data-ttu-id="37ed0-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-516">Boolean</span></span>|  
|<span data-ttu-id="37ed0-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="37ed0-517">NULL_COLLATION</span></span>|<span data-ttu-id="37ed0-518">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-518">Int32</span></span>|  
|<span data-ttu-id="37ed0-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37ed0-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="37ed0-520">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-520">Int64</span></span>|  
|<span data-ttu-id="37ed0-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-521">COLUMN_NAME</span></span>|<span data-ttu-id="37ed0-522">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-522">String</span></span>|  
|<span data-ttu-id="37ed0-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="37ed0-523">COLUMN_GUID</span></span>|<span data-ttu-id="37ed0-524">Guid</span><span class="sxs-lookup"><span data-stu-id="37ed0-524">Guid</span></span>|  
|<span data-ttu-id="37ed0-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="37ed0-525">COLUMN_PROPID</span></span>|<span data-ttu-id="37ed0-526">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-526">Int64</span></span>|  
|<span data-ttu-id="37ed0-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="37ed0-527">COLLATION</span></span>|<span data-ttu-id="37ed0-528">Int16</span><span class="sxs-lookup"><span data-stu-id="37ed0-528">Int16</span></span>|  
|<span data-ttu-id="37ed0-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="37ed0-529">CARDINALITY</span></span>|<span data-ttu-id="37ed0-530">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="37ed0-530">Decimal</span></span>|  
|<span data-ttu-id="37ed0-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="37ed0-531">PAGES</span></span>|<span data-ttu-id="37ed0-532">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-532">Int32</span></span>|  
|<span data-ttu-id="37ed0-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="37ed0-533">FILTER_CONDITION</span></span>|<span data-ttu-id="37ed0-534">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-534">String</span></span>|  
|<span data-ttu-id="37ed0-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="37ed0-535">INTEGRATED</span></span>|<span data-ttu-id="37ed0-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="37ed0-537">Поставщик OLE DB для Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="37ed0-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="37ed0-538">Драйвер OLE DB для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="37ed0-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="37ed0-539">Таблицы</span><span class="sxs-lookup"><span data-stu-id="37ed0-539">Tables</span></span>  
  
-   <span data-ttu-id="37ed0-540">Столбцы</span><span class="sxs-lookup"><span data-stu-id="37ed0-540">Columns</span></span>  
  
-   <span data-ttu-id="37ed0-541">Процедуры</span><span class="sxs-lookup"><span data-stu-id="37ed0-541">Procedures</span></span>  
  
-   <span data-ttu-id="37ed0-542">Представления</span><span class="sxs-lookup"><span data-stu-id="37ed0-542">Views</span></span>  
  
-   <span data-ttu-id="37ed0-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="37ed0-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="37ed0-544">Таблицы</span><span class="sxs-lookup"><span data-stu-id="37ed0-544">Tables</span></span>  
  
|<span data-ttu-id="37ed0-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="37ed0-545">ColumnName</span></span>|<span data-ttu-id="37ed0-546">DataType</span><span class="sxs-lookup"><span data-stu-id="37ed0-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37ed0-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-547">TABLE_CATALOG</span></span>|<span data-ttu-id="37ed0-548">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-548">String</span></span>|  
|<span data-ttu-id="37ed0-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="37ed0-550">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-550">String</span></span>|  
|<span data-ttu-id="37ed0-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-551">TABLE_NAME</span></span>|<span data-ttu-id="37ed0-552">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-552">String</span></span>|  
|<span data-ttu-id="37ed0-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="37ed0-553">TABLE_TYPE</span></span>|<span data-ttu-id="37ed0-554">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-554">String</span></span>|  
|<span data-ttu-id="37ed0-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="37ed0-555">TABLE_GUID</span></span>|<span data-ttu-id="37ed0-556">Guid</span><span class="sxs-lookup"><span data-stu-id="37ed0-556">Guid</span></span>|  
|<span data-ttu-id="37ed0-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37ed0-557">DESCRIPTION</span></span>|<span data-ttu-id="37ed0-558">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-558">String</span></span>|  
|<span data-ttu-id="37ed0-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="37ed0-559">TABLE_PROPID</span></span>|<span data-ttu-id="37ed0-560">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-560">Int64</span></span>|  
|<span data-ttu-id="37ed0-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37ed0-561">DATE_CREATED</span></span>|<span data-ttu-id="37ed0-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="37ed0-562">DateTime</span></span>|  
|<span data-ttu-id="37ed0-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37ed0-563">DATE_MODIFIED</span></span>|<span data-ttu-id="37ed0-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="37ed0-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="37ed0-565">Столбцы</span><span class="sxs-lookup"><span data-stu-id="37ed0-565">Columns</span></span>  
  
|<span data-ttu-id="37ed0-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="37ed0-566">ColumnName</span></span>|<span data-ttu-id="37ed0-567">DataType</span><span class="sxs-lookup"><span data-stu-id="37ed0-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37ed0-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-568">TABLE_CATALOG</span></span>|<span data-ttu-id="37ed0-569">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-569">String</span></span>|  
|<span data-ttu-id="37ed0-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="37ed0-571">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-571">String</span></span>|  
|<span data-ttu-id="37ed0-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-572">TABLE_NAME</span></span>|<span data-ttu-id="37ed0-573">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-573">String</span></span>|  
|<span data-ttu-id="37ed0-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-574">COLUMN_NAME</span></span>|<span data-ttu-id="37ed0-575">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-575">String</span></span>|  
|<span data-ttu-id="37ed0-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="37ed0-576">COLUMN_GUID</span></span>|<span data-ttu-id="37ed0-577">Guid</span><span class="sxs-lookup"><span data-stu-id="37ed0-577">Guid</span></span>|  
|<span data-ttu-id="37ed0-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="37ed0-578">COLUMN_PROPID</span></span>|<span data-ttu-id="37ed0-579">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-579">Int64</span></span>|  
|<span data-ttu-id="37ed0-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37ed0-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="37ed0-581">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-581">Int64</span></span>|  
|<span data-ttu-id="37ed0-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="37ed0-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="37ed0-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-583">Boolean</span></span>|  
|<span data-ttu-id="37ed0-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="37ed0-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="37ed0-585">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-585">String</span></span>|  
|<span data-ttu-id="37ed0-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="37ed0-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="37ed0-587">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-587">Int64</span></span>|  
|<span data-ttu-id="37ed0-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="37ed0-588">IS_NULLABLE</span></span>|<span data-ttu-id="37ed0-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-589">Boolean</span></span>|  
|<span data-ttu-id="37ed0-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="37ed0-590">DATA_TYPE</span></span>|<span data-ttu-id="37ed0-591">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-591">Int32</span></span>|  
|<span data-ttu-id="37ed0-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="37ed0-592">TYPE_GUID</span></span>|<span data-ttu-id="37ed0-593">Guid</span><span class="sxs-lookup"><span data-stu-id="37ed0-593">Guid</span></span>|  
|<span data-ttu-id="37ed0-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37ed0-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="37ed0-595">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-595">Int64</span></span>|  
|<span data-ttu-id="37ed0-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37ed0-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="37ed0-597">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-597">Int64</span></span>|  
|<span data-ttu-id="37ed0-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37ed0-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="37ed0-599">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-599">Int32</span></span>|  
|<span data-ttu-id="37ed0-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="37ed0-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="37ed0-601">Int16</span><span class="sxs-lookup"><span data-stu-id="37ed0-601">Int16</span></span>|  
|<span data-ttu-id="37ed0-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37ed0-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="37ed0-603">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-603">Int64</span></span>|  
|<span data-ttu-id="37ed0-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="37ed0-605">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-605">String</span></span>|  
|<span data-ttu-id="37ed0-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="37ed0-607">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-607">String</span></span>|  
|<span data-ttu-id="37ed0-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="37ed0-609">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-609">String</span></span>|  
|<span data-ttu-id="37ed0-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="37ed0-611">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-611">String</span></span>|  
|<span data-ttu-id="37ed0-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="37ed0-613">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-613">String</span></span>|  
|<span data-ttu-id="37ed0-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-614">COLLATION_NAME</span></span>|<span data-ttu-id="37ed0-615">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-615">String</span></span>|  
|<span data-ttu-id="37ed0-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="37ed0-617">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-617">String</span></span>|  
|<span data-ttu-id="37ed0-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="37ed0-619">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-619">String</span></span>|  
|<span data-ttu-id="37ed0-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-620">DOMAIN_NAME</span></span>|<span data-ttu-id="37ed0-621">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-621">String</span></span>|  
|<span data-ttu-id="37ed0-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37ed0-622">DESCRIPTION</span></span>|<span data-ttu-id="37ed0-623">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="37ed0-624">Процедуры</span><span class="sxs-lookup"><span data-stu-id="37ed0-624">Procedures</span></span>  
  
|<span data-ttu-id="37ed0-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="37ed0-625">ColumnName</span></span>|<span data-ttu-id="37ed0-626">DataType</span><span class="sxs-lookup"><span data-stu-id="37ed0-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37ed0-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="37ed0-628">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-628">String</span></span>|  
|<span data-ttu-id="37ed0-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="37ed0-630">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-630">String</span></span>|  
|<span data-ttu-id="37ed0-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="37ed0-632">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-632">String</span></span>|  
|<span data-ttu-id="37ed0-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="37ed0-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="37ed0-634">Int16</span><span class="sxs-lookup"><span data-stu-id="37ed0-634">Int16</span></span>|  
|<span data-ttu-id="37ed0-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="37ed0-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="37ed0-636">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-636">String</span></span>|  
|<span data-ttu-id="37ed0-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37ed0-637">DESCRIPTION</span></span>|<span data-ttu-id="37ed0-638">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-638">String</span></span>|  
|<span data-ttu-id="37ed0-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37ed0-639">DATE_CREATED</span></span>|<span data-ttu-id="37ed0-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="37ed0-640">DateTime</span></span>|  
|<span data-ttu-id="37ed0-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37ed0-641">DATE_MODIFIED</span></span>|<span data-ttu-id="37ed0-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="37ed0-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="37ed0-643">Представления</span><span class="sxs-lookup"><span data-stu-id="37ed0-643">Views</span></span>  
  
|<span data-ttu-id="37ed0-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="37ed0-644">ColumnName</span></span>|<span data-ttu-id="37ed0-645">DataType</span><span class="sxs-lookup"><span data-stu-id="37ed0-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37ed0-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-646">TABLE_CATALOG</span></span>|<span data-ttu-id="37ed0-647">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-647">String</span></span>|  
|<span data-ttu-id="37ed0-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="37ed0-649">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-649">String</span></span>|  
|<span data-ttu-id="37ed0-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-650">TABLE_NAME</span></span>|<span data-ttu-id="37ed0-651">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-651">String</span></span>|  
|<span data-ttu-id="37ed0-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="37ed0-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="37ed0-653">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-653">String</span></span>|  
|<span data-ttu-id="37ed0-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="37ed0-654">CHECK_OPTION</span></span>|<span data-ttu-id="37ed0-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-655">Boolean</span></span>|  
|<span data-ttu-id="37ed0-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="37ed0-656">IS_UPDATABLE</span></span>|<span data-ttu-id="37ed0-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-657">Boolean</span></span>|  
|<span data-ttu-id="37ed0-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37ed0-658">DESCRIPTION</span></span>|<span data-ttu-id="37ed0-659">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-659">String</span></span>|  
|<span data-ttu-id="37ed0-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37ed0-660">DATE_CREATED</span></span>|<span data-ttu-id="37ed0-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="37ed0-661">DateTime</span></span>|  
|<span data-ttu-id="37ed0-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37ed0-662">DATE_MODIFIED</span></span>|<span data-ttu-id="37ed0-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="37ed0-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="37ed0-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="37ed0-664">Indexes</span></span>  
  
|<span data-ttu-id="37ed0-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="37ed0-665">ColumnName</span></span>|<span data-ttu-id="37ed0-666">DataType</span><span class="sxs-lookup"><span data-stu-id="37ed0-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37ed0-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-667">TABLE_CATALOG</span></span>|<span data-ttu-id="37ed0-668">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-668">String</span></span>|  
|<span data-ttu-id="37ed0-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="37ed0-670">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-670">String</span></span>|  
|<span data-ttu-id="37ed0-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-671">TABLE_NAME</span></span>|<span data-ttu-id="37ed0-672">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-672">String</span></span>|  
|<span data-ttu-id="37ed0-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37ed0-673">INDEX_CATALOG</span></span>|<span data-ttu-id="37ed0-674">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-674">String</span></span>|  
|<span data-ttu-id="37ed0-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37ed0-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="37ed0-676">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-676">String</span></span>|  
|<span data-ttu-id="37ed0-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-677">INDEX_NAME</span></span>|<span data-ttu-id="37ed0-678">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-678">String</span></span>|  
|<span data-ttu-id="37ed0-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="37ed0-679">PRIMARY_KEY</span></span>|<span data-ttu-id="37ed0-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-680">Boolean</span></span>|  
|<span data-ttu-id="37ed0-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="37ed0-681">UNIQUE</span></span>|<span data-ttu-id="37ed0-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-682">Boolean</span></span>|  
|<span data-ttu-id="37ed0-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="37ed0-683">CLUSTERED</span></span>|<span data-ttu-id="37ed0-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-684">Boolean</span></span>|  
|<span data-ttu-id="37ed0-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="37ed0-685">TYPE</span></span>|<span data-ttu-id="37ed0-686">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-686">Int32</span></span>|  
|<span data-ttu-id="37ed0-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="37ed0-687">FILL_FACTOR</span></span>|<span data-ttu-id="37ed0-688">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-688">Int32</span></span>|  
|<span data-ttu-id="37ed0-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="37ed0-689">INITIAL_SIZE</span></span>|<span data-ttu-id="37ed0-690">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-690">Int32</span></span>|  
|<span data-ttu-id="37ed0-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="37ed0-691">NULLS</span></span>|<span data-ttu-id="37ed0-692">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-692">Int32</span></span>|  
|<span data-ttu-id="37ed0-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="37ed0-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="37ed0-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-694">Boolean</span></span>|  
|<span data-ttu-id="37ed0-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="37ed0-695">AUTO_UPDATE</span></span>|<span data-ttu-id="37ed0-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-696">Boolean</span></span>|  
|<span data-ttu-id="37ed0-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="37ed0-697">NULL_COLLATION</span></span>|<span data-ttu-id="37ed0-698">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-698">Int32</span></span>|  
|<span data-ttu-id="37ed0-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37ed0-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="37ed0-700">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-700">Int64</span></span>|  
|<span data-ttu-id="37ed0-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="37ed0-701">COLUMN_NAME</span></span>|<span data-ttu-id="37ed0-702">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-702">String</span></span>|  
|<span data-ttu-id="37ed0-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="37ed0-703">COLUMN_GUID</span></span>|<span data-ttu-id="37ed0-704">Guid</span><span class="sxs-lookup"><span data-stu-id="37ed0-704">Guid</span></span>|  
|<span data-ttu-id="37ed0-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="37ed0-705">COLUMN_PROPID</span></span>|<span data-ttu-id="37ed0-706">Int64</span><span class="sxs-lookup"><span data-stu-id="37ed0-706">Int64</span></span>|  
|<span data-ttu-id="37ed0-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="37ed0-707">COLLATION</span></span>|<span data-ttu-id="37ed0-708">Int16</span><span class="sxs-lookup"><span data-stu-id="37ed0-708">Int16</span></span>|  
|<span data-ttu-id="37ed0-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="37ed0-709">CARDINALITY</span></span>|<span data-ttu-id="37ed0-710">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="37ed0-710">Decimal</span></span>|  
|<span data-ttu-id="37ed0-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="37ed0-711">PAGES</span></span>|<span data-ttu-id="37ed0-712">Int32</span><span class="sxs-lookup"><span data-stu-id="37ed0-712">Int32</span></span>|  
|<span data-ttu-id="37ed0-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="37ed0-713">FILTER_CONDITION</span></span>|<span data-ttu-id="37ed0-714">Строковое</span><span class="sxs-lookup"><span data-stu-id="37ed0-714">String</span></span>|  
|<span data-ttu-id="37ed0-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="37ed0-715">INTEGRATED</span></span>|<span data-ttu-id="37ed0-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="37ed0-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37ed0-717">См. также</span><span class="sxs-lookup"><span data-stu-id="37ed0-717">See also</span></span>
- [<span data-ttu-id="37ed0-718">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="37ed0-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
