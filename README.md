def between_markers(text: str, begin: str, end: str) -> str:
    """
        returns substring between two given markers
    """
    a = 0   # заводим переменную-счётчик для начального символа
    b = 0   # заводим переменную-счётчик для конечного символа
    c = 0   # заводим переменную, которая примет значение первого счётчика
    for i in text:  # проходим значения заданной строки
        a += 1  # увеличиваем первый счётчик
        b += 1  # увеличиваем второй счётчик
        if i == begin:  # при прохождении начального символа
            c = a   # переменная принимает значение первого счётчика
        if i == end:    # при прохождении конечного символа
            break   # останавливаем процесс
    return text[c:b -1] # выводим значения строки в диапазоне от начального символа до конечного, исключая его самого


if __name__ == '__main__':
    print('Example:')
    print(between_markers('What is [apple]', '[', ']'))

    # These "asserts" are used for self-checking and not for testing
    assert between_markers('What is >apple<', '>', '<') == "apple"
    assert between_markers('What is [apple]', '[', ']') == "apple"
    assert between_markers('What is ><', '>', '<') == ""
    assert between_markers('>apple<', '>', '<') == "apple"
    print('Wow, you are doing pretty good. Time to check it!')
