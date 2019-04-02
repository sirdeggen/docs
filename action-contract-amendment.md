


# Contract Amendment Action

Contract Amendment Action - the issuer can initiate an amendment to the contract establishment metadata. The ability to make an amendment to the contract is restricted by the Authorization Flag set on the current revision of Contract Formation action.

The following breaks down the construction of a Contract Amendment Action. The action is constructed by building a single string from each of the elements in order.

<div class="ritz grid-container" dir="ltr">
    <table class="waffle" cellspacing="0" cellpadding="0" table-layout=fixed width=100%>
         <tr style='height:19px;'>
            <th style="width:9%" class="s0">Label</th>
            <th style="width:9%" class="s1">Name</th>
            <th style="width:2%" class="s1">Bytes</th>
            <th style="width:25%" class="s1">Example Values</th>
            <th style="width:36%" class="s1">Comments</th>
            <th style="width:5%" class="s1">Data Type</th>
            <th class="s1">Amendment Restrictions</th>
        </tr>
        <tr>
            <td class="c5" colspan="7">
                <a href="javascript:;" data-popover="type-Header">
                   Header - Click to show content
                </a>
             </td>
        </tr>
        <tr>
            <td class="c9">Change Issuer Address</td>
            <td class="c10">ChangeIssuerAddress</td>
            <td class="c10">0</td>
            <td class="c10">1</td>
            <td class="c10"><abbr title="1 - Yes, 0 - No.  Used to change the issuer address.  The new issuer address must be in the input[1] position.">1 - Yes, 0 - No.  Used to change the issuer address.  The new issuer address must be in th ...</abbr></td>
            <td class="c10">bool</td>
            <td class="c10"></td>
        </tr>
        <tr>
            <td class="c9">Change Operator Address</td>
            <td class="c10">ChangeOperatorAddress</td>
            <td class="c10">0</td>
            <td class="c10">1</td>
            <td class="c10"><abbr title="1 - Yes, 0 - No.  Used to change the smart contract operator address.  The new operator address must be in the input[1] position.">1 - Yes, 0 - No.  Used to change the smart contract operator address.  The new operator ad ...</abbr></td>
            <td class="c10">bool</td>
            <td class="c10"></td>
        </tr>
        <tr>
            <td class="c9">Contract Revision</td>
            <td class="c10">ContractRevision</td>
            <td class="c10">4</td>
            <td class="c10">42</td>
            <td class="c10">Counter 0 to (2^32)-1</td>
            <td class="c10">uint</td>
            <td class="c10"></td>
        </tr>
        <tr>
            <td class="c5" colspan="7">
                <a href="javascript:;" data-popover="type-Amendment">
                   Amendments - Click to show content
                </a>
            </td>
        </tr>
        <tr>
            <td class="c5" colspan="7">
                <a href="javascript:;" data-popover="type-TxId">
                   Ref Tx ID - Click to show content
                </a>
            </td>
        </tr>
    </table>
</div>

##Contract Amendment Action Transaction Summary

<div class="ritz grid-container" dir="ltr">
    <table class="waffle" cellspacing="0" cellpadding="0" table-layout=fixed width=100%>
         <tr style='height:19px;'>
            <th class="s0" colspan="6">Smart Contract Operator Fee: 0</th>
       </tr>
         <tr style='height:19px;'>
            <th style="width:10%" class="s0">Index (input)</th>
            <th style="width:20%" class="s1">Txn inputs</th>
            <th style="width:20%" class="s1">Comments</th>
            <th style="width:10%" class="s1">Index (output)</th>
            <th style="width:20%" class="s1">Txn outputs</th>
            <th class="s1">Comments</th>
       </tr>


       <tr>
            <td class="c5">0</td>
            <td class="c6">Issuer's Public Address</td>
            <td class="c6"></td>
            <td class="c10">0</td>
            <td class="c10">Contract Public Address</td>
            <td class="c10"></td>
        </tr>

       <tr>
            <td class="c5">1</td>
            <td class="c6">New Issuer Public Address</td>
            <td class="c6">Only treated as the new Issuer address when the Change Issuer Address flag is set to Y.</td>
            <td class="c10"></td>
            <td class="c10"></td>
            <td class="c10"></td>
        </tr>

    </table>
</div>



<div class="ui modal" id="type-Header">
    <i class="close icon"></i>
    <div class="content docs-content">
        <table class="ui table">
            <tr style='height:19px;'>
                <th style="width:5%" class="s1">Label</th>
                <th style="width:9%" class="s1">Name</th>
                <th style="width:3%" class="s1">Bytes</th>
                <th style="width:33%" class="s1">Example Values</th>
                <th style="width:26%" class="s1">Comments</th>
                <th style="width:5%" class="s1">Data Type</th>
                <th class="s2">Amendment Restrictions</th>
            </tr>
        </table>
    </div>
</div>

<div class="ui modal" id="type-Amendment">
    <i class="close icon"></i>
    <div class="content docs-content">
        <table class="ui table">
            <tr style='height:19px;'>
                <th style="width:5%" class="s1">Label</th>
                <th style="width:9%" class="s1">Name</th>
                <th style="width:3%" class="s1">Bytes</th>
                <th style="width:33%" class="s1">Example Values</th>
                <th style="width:26%" class="s1">Comments</th>
                <th style="width:5%" class="s1">Data Type</th>
                <th class="s2">Amendment Restrictions</th>
            </tr>
            <tr>
                <td class="c10">Field Index</td>
                <td class="c10">FieldIndex</td>
                <td class="c10">1</td>
                <td class="c10" style="word-break:break-all">2</td>
                <td class="c10">Index of the field to be amended.</td>
                <td class="c10">uint</td>
                <td class="c10">A field with a complex array type uses the same FieldIndex value for all elements. For example, in C1 the VotingSystems field is FieldIndex 16. Indexes are zero based.</td>
            </tr>
            <tr>
                <td class="c10">Element</td>
                <td class="c10">Element</td>
                <td class="c10">2</td>
                <td class="c10" style="word-break:break-all">0</td>
                <td class="c10">Specifies the element of the complex array type to be amended. This only applies to array types, and has no meaning for a simple type such as uint64, string, byte or byte[]. Specifying a value > 0 for a simple type will result in a Rejection.</td>
                <td class="c10">uint</td>
                <td class="c10">To specify the 3rd VotingSystem of a Contract, the value 2 would be given. Indexes are zero based.</td>
            </tr>
            <tr>
                <td class="c10">Subfield Index</td>
                <td class="c10">SubfieldIndex</td>
                <td class="c10">1</td>
                <td class="c10" style="word-break:break-all">1</td>
                <td class="c10">Index of the subfield to be amended. This only applies to specific fields of an element in an array. This is used to specify which field of the array element the amendment applies to.</td>
                <td class="c10">uint</td>
                <td class="c10">For example to specify the 2nd field of a VotingSystem, value 1 would be given.</td>
            </tr>
            <tr>
                <td class="c10">Operation</td>
                <td class="c10">Operation</td>
                <td class="c10">1</td>
                <td class="c10" style="word-break:break-all">0</td>
                <td class="c10">0 = Modify. 1 = Add an element to the data to the array of elements. 2 = Delete the element listed in the Element field. The Add and Delete operations only apply to a particilar element of a complex array type. For example, it could be used to remove a particular VotingSystem from a Contract.</td>
                <td class="c10">uint</td>
                <td class="c10"></td>
            </tr>
            <tr>
                <td class="c10">Data</td>
                <td class="c10">Data</td>
                <td class="c10">32</td>
                <td class="c10" style="word-break:break-all"></td>
                <td class="c10">New data for the amended subfield. Data type depends on the the type of the field being amended.</td>
                <td class="c10">varchar</td>
                <td class="c10">The bytes should be in an format appropriate for the field being modified.</td>
            </tr>
        </table>
    </div>
</div>

