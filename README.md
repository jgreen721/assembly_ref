# Assembly Language GIST (ARM)

### Registers/Memory Stack

### global variables/declarations.

            .global _start           <--- global var declaration/ declare _start


            _start:                    <--- tells assembly where to start. acts as main/mount function

      ACTION DESTINATION, ARGUMENTS

      MOV R0 #4      <--  Moves 4 into R0  (numbers will be in hex)
      MOV R1 #12     <--  Moves 12 into R1, 12 == C, so

                        REGISTER    VALUE
                            R0      00000004
                            R1      0000000C

    ADD R2, R0,R1     <-- Moves R0 + R1 or 16 into R3

                           REGISTER    VALUE
                            R0      00000004
                            R1      0000000C
                            R2      00000010

# Accessing the Stack

                .global _start
                        _start:

                        LDR R0, =list <-- Loads list(from first entry(ie, list[0])).
                        LDR R1, [R0,#4] Each list value after is a neighbor in memory so can be traversed
                        LDR R2, [R0,#8]! But hex/reg conversion translates to 4 = 1, so moving 1 would be #4,
                        LDR R3, [R0],#4 moving 2 as #8 and so on.

                   REGISTER    VALUE
                            R0      00000010          <-- address ref to stack memory
                            R1      00000005
                            R2      00000000

                            R0 updates to 00000014    ** preincrement(normal behavior)

                            R0      00000014          <-- address ref to stack memory
                            R1      00000005
                            R2      00000005

                            R0 updates to 00000018       ** post increment (notice R1 == R2)

                .data              <-- data declaration. Puttin a list into stack memory

                list:               .word is datatype(assembly datatypes are datalength measurement terms
                word 4,5,-2,1,7
                                TermMap:{
                                     word:8 bit
                                    half-word:4 bit
                                    byte:1(2?) bit
                                        }

## Operations

                    LDR R0, =nums_array
                    LDR R1, [R0,#4]!
                    LDR R2, [R0,#4]!
                    SUB R3, R1,R2               <-- loads nums_array, increments, stores first value
                                                     in R1, increments loads values
                                                      in R2. Performs subtraction and stores in R3

                    SUM, SUB, MULT
                    Negative Number Concern -- tack on S (SUBS) to cue cpsr N flag to distinguish negative from large number (ie: 1-2 = FFFFFFE, FFFFFFF-1 = FFFFFFE). Does perform additional operation so 'tack with purpose'. (know expected input).

                    Large Number overflow concern -- tack on S (SUMS, MULS) and if number is bigger than 32 bit (0xFFFFFFFF) than you'll get a carry-over flag. Same concern, additonal operation so use with purpose.

                                                         cpsr 0000001d3 (no flags on/normal state)
                    Flags:{
                        8: negative,                      cpsr 800001d3
                        2: carry-over                     cpsr 200001d3
                    }

