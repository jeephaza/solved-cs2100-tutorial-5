Download Link: https://assignmentchef.com/product/solved-cs2100-tutorial-5
<br>
D1. Refer to the following two MIPS instructions:

<ol>

 <li><strong>add $t0, $s0, $s1 </strong>ii. <strong>bne $24, $25, finish </strong></li>

</ol>

Assume that the instruction at label “<strong>finish</strong>” in (ii) is three instructions after <strong>bne</strong>.

For each of the above two instructions, do the following:

<ul>

 <li>Write out the instruction in hexadecimal representation.</li>

 <li>What are the values of the following control signals: <strong>RegDst</strong>, <strong>RegWrite</strong>, and <strong>Branch</strong>?</li>

 <li>What is the register number supplied to the register file’s “Read Register 1” (RR1) input? How about “Read Register 2” (RR2)? Are these registers’ contents utilized in the ALU stage?</li>

 <li>What is the register number supplied to the register file’s “Write register” (WR) input? Is this register actually written?</li>

</ul>




The answers for (i) are given below.




(a) $t0 = $8; $s0 = $16; $s1 = $17  <strong>add $t0, $s0, $s1</strong>:

000000 10000 10001 01000 00000 100000 = <strong>0x02114020</strong>

(b)

<table width="438">

 <tbody>

  <tr>

   <td width="90">Instruction</td>

   <td width="116">RegDst</td>

   <td width="114">RegWrite</td>

   <td width="118">Branch</td>

  </tr>

  <tr>

   <td width="90"><strong>add </strong></td>

   <td width="116">1</td>

   <td width="114">1</td>

   <td width="118">0</td>

  </tr>

 </tbody>

</table>




(c)

<table width="568">

 <tbody>

  <tr>

   <td width="90">Instruction</td>

   <td width="128">Read Register 1</td>

   <td width="113">Used in ALU?</td>

   <td width="123">Read Register 2</td>

   <td width="113">Used in ALU?</td>

  </tr>

  <tr>

   <td width="90"><strong>add </strong></td>

   <td width="128">16 (100002)</td>

   <td width="113">Yes</td>

   <td width="123">17 (100012)</td>

   <td width="113">Yes</td>

  </tr>

 </tbody>

</table>




(d)

<table width="407">

 <tbody>

  <tr>

   <td width="90">Instruction</td>

   <td width="128">Write register</td>

   <td width="189">Actually written?</td>

  </tr>

  <tr>

   <td width="90"><strong>add </strong></td>

   <td width="128">8 (010002)</td>

   <td width="189">Yes</td>

  </tr>

 </tbody>

</table>




<strong><em>             </em></strong>

<h1>Tutorial Questions</h1>

Questions 1 and 2 refer to the complete datapath and control design covered in lectures #11 and #12. Please use the diagram in Lecture #12 slide 29 or in the COD MIPS 4<sup>th</sup> edition textbook, Figure 4.17. For your convenience, Lecture #12 slide 29 is also included at the end of this tutorial sheet.

<ol>

 <li>Let us perform a complete trace to understand the working of the complete datapath and control implementation. Given the following three hexadecimal representations of MIPS instructions:</li>

 <li><strong>0x8df80000: lw $24, 0($15) </strong>ii. <strong>0x1023000C:  beq $1, $3, 12 </strong>iii.<strong>  0x0285c822: sub $25, $20, $5 </strong></li>

</ol>

For each instruction encoding, do the following:

<ol>

 <li>Fill in the tables below. The first table concerns with the various data (information) at each of the datapath elements, while the second table records the control signals generated. Use the notation $8 to represent register number 8, [$8] to represent the content of register number 8 and Mem(X) to represent the memory data at address</li>

</ol>

X.




<table width="534">

 <tbody>

  <tr>

   <td width="60"> </td>

   <td colspan="2" width="120"><strong>Registers File </strong></td>

   <td width="60"> </td>

   <td colspan="2" width="120"><strong>ALU </strong></td>

   <td colspan="2" width="174"><strong>Data Memory </strong></td>

  </tr>

  <tr>

   <td width="60">RR1</td>

   <td width="60">RR2</td>

   <td width="60">WR</td>

   <td width="60">WD</td>

   <td width="54">Opr1</td>

   <td width="66">Opr2</td>

   <td width="85">Address</td>

   <td width="89">Write Data</td>

  </tr>

  <tr>

   <td width="60"> </td>

   <td width="60"> </td>

   <td width="60"> </td>

   <td width="60"> </td>

   <td width="54"> </td>

   <td width="66"> </td>

   <td width="85"> </td>

   <td width="89"> </td>

  </tr>

  <tr>

   <td width="60"> </td>

   <td width="60"> </td>

   <td width="60"> </td>

   <td width="60"> </td>

   <td width="54"> </td>

   <td width="66"> </td>

   <td width="85"> </td>

   <td width="89"> </td>

  </tr>

  <tr>

   <td width="60"> </td>

   <td width="60"> </td>

   <td width="60"> </td>

   <td width="60"> </td>

   <td width="54"> </td>

   <td width="66"> </td>

   <td width="85"> </td>

   <td width="89"> </td>

  </tr>

 </tbody>

</table>




[Wr = Write; Rd = Read; M = Mem; R = Reg]

<table width="573">

 <tbody>

  <tr>

   <td width="66"><strong>RegDst </strong></td>

   <td width="64"><strong>RegWr </strong></td>

   <td width="71"><strong>ALUSrc </strong></td>

   <td width="63"><strong>MRd </strong></td>

   <td width="63"><strong>MWr </strong></td>

   <td width="60"><strong>MToR </strong></td>

   <td width="48"><strong>Brch </strong></td>

   <td width="65"><strong>ALUop </strong></td>

   <td width="72"><strong>ALUctrl </strong></td>

  </tr>

  <tr>

   <td width="66"> </td>

   <td width="64"> </td>

   <td width="71"> </td>

   <td width="63"> </td>

   <td width="63"> </td>

   <td width="60"> </td>

   <td width="48"> </td>

   <td width="65"> </td>

   <td width="72"> </td>

  </tr>

  <tr>

   <td width="66"> </td>

   <td width="64"> </td>

   <td width="71"> </td>

   <td width="63"> </td>

   <td width="63"> </td>

   <td width="60"> </td>

   <td width="48"> </td>

   <td width="65"> </td>

   <td width="72"> </td>

  </tr>

  <tr>

   <td width="66"> </td>

   <td width="64"> </td>

   <td width="71"> </td>

   <td width="63"> </td>

   <td width="63"> </td>

   <td width="60"> </td>

   <td width="48"> </td>

   <td width="65"> </td>

   <td width="72"> </td>

  </tr>

 </tbody>

</table>




<ol>

 <li>Indicate the value of the PC after the instruction is executed.</li>

</ol>







<ol start="2">

 <li>With the complete datapath and control design, it is now possible to estimate the latency (time needed for a task) for the various type of instructions. Given below are the resource latencies of the various hardware components (ps = picoseconds = 10<sup>-12</sup> second):</li>

</ol>

<table width="569">

 <tbody>

  <tr>

   <td width="63"><strong>Inst-</strong><strong>Mem </strong></td>

   <td width="58"><strong>Adder </strong></td>

   <td width="54"><strong>MUX </strong></td>

   <td width="56"><strong>ALU </strong></td>

   <td width="71"><strong>Reg-File </strong></td>

   <td width="63"><strong>Data-</strong><strong>Mem </strong></td>

   <td width="94"><strong>Control/ </strong><strong>ALUControl </strong></td>

   <td width="110"><strong>Left-shift/ SignExtend/ AND </strong></td>

  </tr>

  <tr>

   <td width="63">400ps</td>

   <td width="58">100ps</td>

   <td width="54">30ps</td>

   <td width="56">120ps</td>

   <td width="71">200ps</td>

   <td width="63">350ps</td>

   <td width="94">100ps</td>

   <td width="110">20ps</td>

  </tr>

 </tbody>

</table>




Give the estimated latencies for the following MIPS instructions:

<ul>

 <li>“SUB” instruction (e.g. <strong>sub $25, $20, $5</strong>)</li>

 <li>“LW” instruction (e.g. <strong>lw $24, 0($15)</strong>)</li>

 <li>“BEQ” instruction (e.g. <strong>beq $1, $3, 12</strong>)</li>

</ul>




What do you think the <strong>cycle time</strong> should be for this particular processor implementation?

<em>Hint:</em> First, you need to find out the <strong>critical path</strong> of an instruction, i.e. the path that takes the longest time to complete. Note that there could be several <u>parallel paths</u> that work more or less simultaneously.







<ol start="3">

 <li>[AY2013/14 Semester 2 Term Test #2]</li>

</ol>

Mr. De Blunder made a <strong><em>huge </em></strong>mistake while making his own non-pipelined MIPS processor. He accidentally <strong>swapped the two input ports for the RegDst multiplexer: </strong>

<strong> </strong>




For each of the following instructions, give:

<ol>

 <li>One example where the incorrect processor still gives the <strong>right execution result.</strong> ii. One example where the incorrect processor gives the <strong>wrong execution result</strong>.</li>

</ol>

If there is no suitable answer, please indicate “No Answer”.




<ul>

 <li><strong>add</strong> (Addition)</li>

 <li><strong>lw</strong> (Load Word)</li>

</ul>

<strong>beq</strong> (branch-if-equal), provide the branch offset as immediate value