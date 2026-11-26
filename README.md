```csharp
using System;

public static class RotationalCipher
{
    public static string Rotate(string text, int shiftKey)
    {
        char[] buffer = text.ToCharArray();

        for (int i = 0; i < buffer.Length; i++)
        {
            char c = buffer[i];
            if (char.IsLetter(c))
            {
                char offset = char.IsUpper(c) ? 'A' : 'a';
                buffer[i] = (char)(((c - offset + shiftKey) % 26 + 26) % 26 + offset);
            }
        }

        return new string(buffer);
    }
}
```
