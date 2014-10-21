library ieee;
use ieee.std_logic_1164.all;
use ieee.std_logic_Unsigned.all;
use ieee.std_logic_Arith.all;

--f=500Hz

--0 1 2 3 4 5 6 7 
--x x x x x x x x 0
--x x x x x x x x 1
--x x x x x x x x 2
--x x x x x x x x 3
--x x x x x x x x 4
--x x x x x x x x 5
--x x x x x x x x 6
--x x x x x x x x 7


entity lattice IS
port(clk:in std_logic;
     colorr:out std_logic_vector(7 downto 0); --red display 
     colorg:out std_logic_vector(7 downto 0); --green 
     list:out std_logic_vector(7 downto 0)    --judge
     );
end lattice;

architecture a of lattice IS
     signal sol:std_logic_vector(7 downto 0);--sol:signal of list   
     signal gstate0,gstate1,gstate2,gstate3,gstate4,gstate5,gstate6,gstate7:std_logic_vector(7 downto 0);--8 lines' display of green
     signal rstate0,rstate1,rstate2,rstate3,rstate4,rstate5,rstate6,rstate7:std_logic_vector(7 downto 0);--8 lines' display of red
     signal sw1:std_logic; --Control the direction of movement of the hourglass.sw=0->red to green while sw=1->green to red
     signal count:std_logic_vector(3 downto 0);
     signal fcount:std_logic_vector(8 downto 0);
     signal btn0:std_logic;

begin
   start:process(btn0) 
   begin    
       if (btn0='0')then
                          gstate0<= "00000000";--0
                          gstate1<= "00000000";
                          gstate2<= "00000000";
                          gstate3<= "00000000";
                          gstate4<= "00010000";
                          gstate5<= "00111000";
                          gstate6<= "01111100";
                          gstate7<= "11111111";
                          rstate0<= gstate7;
                          rstate1<= gstate6;
                          rstate2<= gstate5;
                          rstate3<= gstate4;
                          rstate4<= gstate3;
                          rstate5<= gstate2;
                          rstate6<= gstate1;
                          rstate7<= gstate0;
        end if;                   
   end process start;                       
          
   go:process(clk,sw1,btn0)
   begin   
       if (clk='1' and sw1='0' and btn0='1')then
       fcount<=fcount+1;
       end if;
       if (fcount>="111110100")then
       count<=count+1;
       fcount<="000000000";
       end if;
   end process go;
      
   re:process(clk,sw1,btn0)
   begin  
       if (clk='0' and sw1='1' and btn0='1')then
       fcount<=fcount+1;
       end if;
       if (fcount>="111110100")then
       count<=count-1;
       fcount<="000000000";
       end if;
   end process re;    

   change:process(count)          
   begin
       case count IS
           when"0000" =>  gstate0<= "00010000";--1
                          gstate1<= "00000000";
                          gstate2<= "00000000";
                          gstate3<= "00000000";
                          gstate4<= "00010000";
                          gstate5<= "00111000";
                          gstate6<= "01111100";
                          gstate7<= "11101111";
                          rstate0<= gstate7;
                          rstate1<= gstate6;
                          rstate2<= gstate5;
                          rstate3<= gstate4;
                          rstate4<= gstate3;
                          rstate5<= gstate2;
                          rstate6<= gstate1;
                          rstate7<= gstate0;
                                          
           when"0001" =>  gstate0<= "00110000";--2
                          gstate1<= "00000000";
                          gstate2<= "00000000";
                          gstate3<= "00000000";
                          gstate4<= "00010000";
                          gstate5<= "00111000";
                          gstate6<= "01111100";
                          gstate7<= "11001110";
                          rstate0<= gstate7;
                          rstate1<= gstate6;
                          rstate2<= gstate5;
                          rstate3<= gstate4;
                          rstate4<= gstate3;
                          rstate5<= gstate2;
                          rstate6<= gstate1;
                          rstate7<= gstate0;
                          
           when"0010" =>  gstate0<= "00111000";--3
                          gstate1<= "00000000";
                          gstate2<= "00000000";
                          gstate3<= "00000000";
                          gstate4<= "00010000";
                          gstate5<= "00111000";
                          gstate6<= "01111100";
                          gstate7<= "11000110";
                          rstate0<= gstate7;
                          rstate1<= gstate6;
                          rstate2<= gstate5;
                          rstate3<= gstate4;
                          rstate4<= gstate3;
                          rstate5<= gstate2;
                          rstate6<= gstate1;
                          rstate7<= gstate0;
                          
           when"0011" =>  gstate0<= "01111000";--4
                          gstate1<= "00000000";
                          gstate2<= "00000000";
                          gstate3<= "00000000";
                          gstate4<= "00010000";
                          gstate5<= "00111000";
                          gstate6<= "01111100";
                          gstate7<= "10000110";
                          rstate0<= gstate7;
                          rstate1<= gstate6;
                          rstate2<= gstate5;
                          rstate3<= gstate4;
                          rstate4<= gstate3;
                          rstate5<= gstate2;
                          rstate6<= gstate1;
                          rstate7<= gstate0;
                          
           when"0100" =>  gstate0<= "01111100";--5
                          gstate1<= "00000000";
                          gstate2<= "00000000";
                          gstate3<= "00000000";
                          gstate4<= "00010000";
                          gstate5<= "00111000";
                          gstate6<= "01111100";
                          gstate7<= "10000010";
                          rstate0<= gstate7;
                          rstate1<= gstate6;
                          rstate2<= gstate5;
                          rstate3<= gstate4;
                          rstate4<= gstate3;
                          rstate5<= gstate2;
                          rstate6<= gstate1;
                          rstate7<= gstate0;
                          
           when"0101" =>  gstate0<= "11111100";--6
                          gstate1<= "00000000";
                          gstate2<= "00000000";
                          gstate3<= "00000000";
                          gstate4<= "00010000";
                          gstate5<= "00111000";
                          gstate6<= "01111100";
                          gstate7<= "00000010";
                          rstate0<= gstate7;
                          rstate1<= gstate6;
                          rstate2<= gstate5;
                          rstate3<= gstate4;
                          rstate4<= gstate3;
                          rstate5<= gstate2;
                          rstate6<= gstate1;
                          rstate7<= gstate0;
                          
           when"0110" =>  gstate0<= "11111110";--7
                          gstate1<= "00000000";
                          gstate2<= "00000000";
                          gstate3<= "00000000";
                          gstate4<= "00010000";
                          gstate5<= "00111000";
                          gstate6<= "01111100";
                          gstate7<= "00000000";
                          rstate0<= gstate7;
                          rstate1<= gstate6;
                          rstate2<= gstate5;
                          rstate3<= gstate4;
                          rstate4<= gstate3;
                          rstate5<= gstate2;
                          rstate6<= gstate1;
                          rstate7<= gstate0;
                          
           when"0111" =>  gstate0<= "11111110";--8
                          gstate1<= "00010000";
                          gstate2<= "00000000";
                          gstate3<= "00000000";
                          gstate4<= "00010000";
                          gstate5<= "00111000";
                          gstate6<= "01101100";
                          gstate7<= "00000000";
                          rstate0<= gstate7;
                          rstate1<= gstate6;
                          rstate2<= gstate5;
                          rstate3<= gstate4;
                          rstate4<= gstate3;
                          rstate5<= gstate2;
                          rstate6<= gstate1;
                          rstate7<= gstate0;
                          
           when"1000" =>  gstate0<= "11111110";--9
                          gstate1<= "00110000";
                          gstate2<= "00000000";
                          gstate3<= "00000000";
                          gstate4<= "00010000";
                          gstate5<= "00111000";
                          gstate6<= "01001100";
                          gstate7<= "00000000";
                          rstate0<= gstate7;
                          rstate1<= gstate6;
                          rstate2<= gstate5;
                          rstate3<= gstate4;
                          rstate4<= gstate3;
                          rstate5<= gstate2;
                          rstate6<= gstate1;
                          rstate7<= gstate0;
                          
           when"1001" =>  gstate0<= "11111110";--10
                          gstate1<= "00111000";
                          gstate2<= "00000000";
                          gstate3<= "00000000";
                          gstate4<= "00010000";
                          gstate5<= "00111000";
                          gstate6<= "01000100";
                          gstate7<= "00000000";
                          rstate0<= gstate7;
                          rstate1<= gstate6;
                          rstate2<= gstate5;
                          rstate3<= gstate4;
                          rstate4<= gstate3;
                          rstate5<= gstate2;
                          rstate6<= gstate1;
                          rstate7<= gstate0;
                          
           when"1010" =>  gstate0<= "11111110";--11
                          gstate1<= "01111000";
                          gstate2<= "00000000";
                          gstate3<= "00000000";
                          gstate4<= "00010000";
                          gstate5<= "00111000";
                          gstate6<= "00000100";
                          gstate7<= "00000000";
                          rstate0<= gstate7;
                          rstate1<= gstate6;
                          rstate2<= gstate5;
                          rstate3<= gstate4;
                          rstate4<= gstate3;
                          rstate5<= gstate2;
                          rstate6<= gstate1;
                          rstate7<= gstate0;
                          
           when"1011" =>  gstate0<= "11111110";--12
                          gstate1<= "01111100";
                          gstate2<= "00000000";
                          gstate3<= "00000000";
                          gstate4<= "00010000";
                          gstate5<= "00111000";
                          gstate6<= "00000000";
                          gstate7<= "00000000";
                          rstate0<= gstate7;
                          rstate1<= gstate6;
                          rstate2<= gstate5;
                          rstate3<= gstate4;
                          rstate4<= gstate3;
                          rstate5<= gstate2;
                          rstate6<= gstate1;
                          rstate7<= gstate0;
                          
           when"1100" =>  gstate0<= "11111110";--13
                          gstate1<= "01111100";
                          gstate2<= "00010000";
                          gstate3<= "00000000";
                          gstate4<= "00010000";
                          gstate5<= "00101000";
                          gstate6<= "00000000";
                          gstate7<= "00000000";
                          rstate0<= gstate7;
                          rstate1<= gstate6;
                          rstate2<= gstate5;
                          rstate3<= gstate4;
                          rstate4<= gstate3;
                          rstate5<= gstate2;
                          rstate6<= gstate1;
                          rstate7<= gstate0;
                            
           when"1101" =>  gstate0<= "11111110";--14
                          gstate1<= "01111100";
                          gstate2<= "00110000";
                          gstate3<= "00000000";
                          gstate4<= "00010000";
                          gstate5<= "00001000";
                          gstate6<= "00000000";
                          gstate7<= "00000000";
                          rstate0<= gstate7;
                          rstate1<= gstate6;
                          rstate2<= gstate5;
                          rstate3<= gstate4;
                          rstate4<= gstate3;
                          rstate5<= gstate2;
                          rstate6<= gstate1;
                          rstate7<= gstate0;
                          
           when"1110" =>  gstate0<= "11111110";--15
                          gstate1<= "01111100";
                          gstate2<= "00111000";
                          gstate3<= "00000000";
                          gstate4<= "00010000";
                          gstate5<= "00000000";
                          gstate6<= "00000000";
                          gstate7<= "00000000";
                          rstate0<= gstate7;
                          rstate1<= gstate6;
                          rstate2<= gstate5;
                          rstate3<= gstate4;
                          rstate4<= gstate3;
                          rstate5<= gstate2;
                          rstate6<= gstate1;
                          rstate7<= gstate0;
                             
           when"1111" =>  gstate0<= "11111110";--16
                          gstate1<= "01111100";
                          gstate2<= "00111000";
                          gstate3<= "00010000";
                          gstate4<= "00000000";
                          gstate5<= "00000000";
                          gstate6<= "00000000";
                          gstate7<= "00000000";
                          rstate0<= gstate7;
                          rstate1<= gstate6;
                          rstate2<= gstate5;
                          rstate3<= gstate4;
                          rstate4<= gstate3;
                          rstate5<= gstate2;
                          rstate6<= gstate1;
                          rstate7<= gstate0;
       end case;
   end process change;                     
end;  
