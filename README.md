# 2-1-multiplexer
here is the code of vhdl for 2*1 multiplexer(test bench)
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
entity tb_mux2to1 is
end tb_mux2to1;
architecture behavior of tb_mux2to1 is
 component mux2to1
 Port (
 A : in STD_LOGIC;
 B : in STD_LOGIC;
 SEL : in STD_LOGIC;
 Y : out STD_LOGIC
 );
 end component;
 signal A, B, SEL, Y : STD_LOGIC := '0';
begin
 uut: mux2to1 PORT MAP (
 A => A,
 B => B,
 SEL => SEL,
 Y => Y
 );
 stim_proc: process
 begin
 A <= '0'; B <= '0'; SEL <= '0'; wait for 10 ns;
 A <= '0'; B <= '1'; SEL <= '0'; wait for 10 ns;
 A <= '1'; B <= '0'; SEL <= '0'; wait for 10 ns;
 A <= '1'; B <= '1'; SEL <= '0'; wait for 10 ns;
 A <= '0'; B <= '0'; SEL <= '1'; wait for 10 ns;
 A <= '0'; B <= '1'; SEL <= '1'; wait for 10 ns;
 A <= '1'; B <= '0'; SEL <= '1'; wait for 10 ns;
 A <= '1'; B <= '1'; SEL <= '1'; wait for 10 ns;
 wait;
 end process;
end;
code for 2*1multiplexer in vhdl design code
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
entity mux2to1 is
 Port (
 A : in STD_LOGIC;
 B : in STD_LOGIC;
 SEL : in STD_LOGIC;
 Y : out STD_LOGIC
 );
end mux2to1;
architecture Behavioral of mux2to1 is
begin
 process(A, B, SEL)
 begin
 if (SEL = '0') then
 Y <= A;
 else
 Y <= B;
 end if;
 end process;
end Behavioral;

