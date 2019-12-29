								###RUBY WARRIOR BEGINER CHALLENGE SOLUTION BY SAMBIT KUMAR MOHANTY
		
		Level 1: Question: -You see before yourself a long hallway with stairs at the end. There is nothing in the way.
		Solution: 
					```ruby
					class Player
						  def play_turn(warrior)
							# cool code goes here
							  warrior.walk!
						  end
					end
					```
		
		Level 2: It is too dark to see anything, but you smell sludge nearby.
		Solution: 		
					```ruby
					class Player
					  def play_turn(warrior)
						# cool code goes here
						if warrior.feel.empty?
						  warrior.walk!
						else
						  warrior.attack!
						end
					  end
					end
					```
		Level 3: The air feels thicker than before. There must be a horde of sludge.
		Solution: 
					```ruby				    
					class Player
					  def play_turn(warrior)
						# cool code goes here
						if warrior.feel.empty? && warrior.health == 20
						  warrior.walk!
						elsif warrior.feel.empty? && warrior.health < 20
						  warrior.rest!
						else
						  warrior.attack!
						end
					  end
					end
					``` 	
		Level 4: You can hear bow strings being stretched. 
		Solution:
					```ruby
					class Player
					  def play_turn(warrior)
						if warrior.feel.enemy?
						   warrior.attack!
						else
						  if warrior.health < 20 && !damage(warrior)
							warrior.rest!
						  else
							warrior.walk!
						  end
						end
						@health = warrior.health
					  end
					  
					  
					  def damage(warrior)
						warrior.health < @health
					  end
					  
					end					
					```		
		Level 5: 
		Solution: 
					```ruby
					class Player
					  def play_turn(warrior)
						# cool code goes here
						if @health.nil?
						  @health = 20
						end
						
						if @health > warrior.health
						  # damaged
						  if warrior.feel.empty?
							warrior.walk!
						  elsif warrior.feel.enemy?
							warrior.attack!
						  end
						elsif warrior.feel.enemy?
						  warrior.attack!
						else
						  if warrior.health < 15
							warrior.rest!
						  elsif warrior.feel.empty?
							warrior.walk!
						  elsif warrior.feel.captive?
							warrior.rescue!
						  end
						end
						
						@health = warrior.health
					  end
					end
					```
					
					
					
					
					
					
					
					
					
					
					
					
					
					
