# String-Compression
Given an array of characters chars, compress it using the following algorithm:

Begin with an empty string s. For each group of consecutive repeating characters in chars:

If the group's length is 1, append the character to s.
Otherwise, append the character followed by the group's length.
The compressed string s should not be returned separately, but instead, be stored in the input character array chars. Note that group lengths that are 10 or longer will be split into multiple characters in chars.

After you are done modifying the input array, return the new length of the array.

You must write an algorithm that uses only constant extra space.

 

Example 1:

Input: chars = ["a","a","b","b","c","c","c"]
Output: Return 6, and the first 6 characters of the input array should be: ["a","2","b","2","c","3"]
Explanation: The groups are "aa", "bb", and "ccc". This compresses to "a2b2c3".
Example 2:

Input: chars = ["a"]
Output: Return 1, and the first character of the input array should be: ["a"]
Explanation: The only group is "a", which remains uncompressed since it's a single character.
Example 3:

Input: chars = ["a","b","b","b","b","b","b","b","b","b","b","b","b"]
Output: Return 4, and the first 4 characters of the input array should be: ["a","b","1","2"].
Explanation: The groups are "a" and "bbbbbbbbbbbb". This compresses to "ab12".
 

Constraints:

1 <= chars.length <= 2000
chars[i] is a lowercase English letter, uppercase English letter, digit, or symbol.

# Explanation & Solution

"String Compression Algorithm” or “Run Length Encoding” happens when you compress a string, and the consecutive duplicates of each string are replaced with the character, followed by the consecutive, repeated character count.

For example:

After string compression, the string “aaaabbcddddd” would return “a4b2c1d5”.

You may not have see such strings in texts, but image and video files almost always have long repeating sequences. Some uses of run length encoding include:

- Compressing faxed documents
- Compressing JPEG images
In case of images, colors are replaced by the character, or color, followed by the number of times that color repeats itself.

Start by taking the first character of the given string and appending it to the compressed string.

Next, count the number of occurrences of that specific character and append it to the compressed string.

Repeat this process for all the characters until the end of the string is reached.

Some run length encoding approaches also use an escape character before the count value. For example, if the file has some numeric character.

With the escape character approach, the string compression of “aaaabbcddddd” would return “aa4bb2cdd5”.

