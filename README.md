i = 1
for movie in sorted_similar_movies:
  index = movie[0]
  title_from_index = movies_data[movies_data.index == index]['title'].values[0]
  if i < 30:
    print(i, '.', title_from_index)
    i += 1

