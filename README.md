
# 1. "명세" 가 곧 코드다 #
## 1-1. There will be code ##
- specification IS code
- some expect programmers won't be needed, because codes will be generated from specs in the future. Wrong.
- higher level domain-specific language will be code, It will still need to be rigorous, accurate, and so formal and detailed that a machine can understand and execute it.

***

# 2. 나쁜 코드를 왜 피해야 하는가? #
## 2-1. Bad code ##
- bad code can bring down the whole company
- adding features before cleaning up the mess will make the code harder to understand, and will eventually make the whole product unmanageable.

## 2-2. The total cost of owning a mess ##
- messy code will force you to understand all the tiny tangles and twists before changing anything, and force you to make more tangles and twists. This will slow down the process and drive the productivity towards zero.
- management will add more staff, hoping that productivity will increase.
- but new staff won't understand the whole mess, so productivity stays the same.
- pressure increases, and more messes are made.

## 2-3. The grand redisign in the sky ##
- team members demand a redisign.
- new "tiger team" is selected, and tries to start over the whold project, and add some new features. old team maintains the current system.
- after 10 years, tiger team finally finishes rebuilding, but original members are already gone.
- new members demand a redisign.
## 2-4. Attitude ##
- stubborn managers, tight schedule, intolerant customers... but baisically, it is your job to defend the code.

## 2-5. The primal conundrum ##
- all developers know that previous messes slow them down, but at the same time they make messes in order to meet the deadline.
- the mess will instantaniously slow you down-the only way to keep the deadline is to keep the code as clean as possible.

***

# 3. "좋은" 코드란 어떤 코드인가? #
## 3-1. The art of clean code? ##
- writing clean code is a lot like painting a picture.
- first, you need to be able to recognize clean code from messy code.
- painstackingly acquired sense of "cleanliness" will acutally give you power to look at a messy module and see options and variations.

## 3-2. What is clean code? ##
- code that is...
- pleasant to read, for you and your collegues.
- efficient. Not only because speed matters, but bad code tempts to grow(metaphor of broken windows)
- detailed. (error handling, memory leak, naming...)
- does one thing well
- written with care

## 3-3. The boy scout rule ##
- "leave the campground cleaner than you found it".

